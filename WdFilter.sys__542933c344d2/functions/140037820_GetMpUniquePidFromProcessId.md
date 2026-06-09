# GetMpUniquePidFromProcessId

- ea: `0x140037820`
- end: `0x140037927`
- name: `GetMpUniquePidFromProcessId`
- size: `263`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x14002f510`
- `0x140036780`
- `0x140063a70`
- `0x140065f00`

## callees

- `0x140003950`
- `0x1400118d0`
- `0x140037820`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x140037863`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140037863`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140037884`
- `ntoskrnl!PsGetProcessCreateTimeQuadPart` at `0x140037884`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400378fd`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400378fd`
- `ntoskrnl!KeBugCheck` at `0x140037915`
- `ntoskrnl!KeBugCheck` at `0x140037915`
- `ntoskrnl!ObfDereferenceObject` at `0x140037898`
- `ntoskrnl!ObfDereferenceObject` at `0x140037898`

## pseudocode

```c
NTSTATUS __fastcall GetMpUniquePidFromProcessId(void *a1, __int64 a2)
{
  int v3; // edi
  NTSTATUS result; // eax
  LONGLONG TimeQuadPart; // rsi
  PEPROCESS Process; // [rsp+20h] [rbp-18h] BYREF

  v3 = (int)a1;
  if ( !a1 || !a2 )
    return -1073741811;
  Process = 0;
  result = PsLookupProcessByProcessId(a1, &Process);
  if ( result < 0 )
  {
    _mm_lfence();
  }
  else
  {
    _InterlockedIncrement64(&ObTotalReferences);
    TimeQuadPart = PsGetProcessCreateTimeQuadPart(Process);
    ObfDereferenceObject(Process);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
    *(_DWORD *)a2 = v3;
    *(_QWORD *)(a2 + 4) = MpFileTimeToUlong64(TimeQuadPart);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140037820  mov     r11, rsp
0x140037823  mov     [r11+18h], rbx
0x140037827  mov     [r11+20h], rsi
0x14003782b  push    rdi
0x14003782c  sub     rsp, 30h
0x140037830  mov     rax, cs:__security_cookie
0x140037837  xor     rax, rsp
0x14003783a  mov     [rsp+38h+var_10], rax
0x14003783f  mov     rbx, rdx
0x140037842  mov     rdi, rcx
0x140037845  test    rcx, rcx
0x140037848  jz      loc_1400378E5
0x14003784e  test    rdx, rdx
0x140037851  jz      loc_1400378E5
0x140037857  lea     rdx, [r11-18h]; Process
0x14003785b  mov     qword ptr [r11-18h], 0
0x140037863  call    cs:__imp_PsLookupProcessByProcessId
0x14003786a  nop     dword ptr [rax+rax+00h]
0x14003786f  test    eax, eax
0x140037871  js      loc_140037922
0x140037877  lock inc cs:ObTotalReferences
0x14003787f  mov     rcx, [rsp+38h+Process]; Process
0x140037884  call    cs:__imp_PsGetProcessCreateTimeQuadPart
0x14003788b  nop     dword ptr [rax+rax+00h]
0x140037890  mov     rcx, [rsp+38h+Process]; Object
0x140037895  mov     rsi, rax
0x140037898  call    cs:__imp_ObfDereferenceObject
0x14003789f  nop     dword ptr [rax+rax+00h]
0x1400378a4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400378a8  lock xadd cs:ObTotalReferences, rcx
0x1400378b1  cmp     rcx, 1
0x1400378b5  js      short loc_1400378EC
0x1400378b7  mov     rcx, rsi
0x1400378ba  mov     [rbx], edi
0x1400378bc  call    MpFileTimeToUlong64
0x1400378c1  mov     [rbx+4], rax
0x1400378c5  xor     eax, eax
0x1400378c7  mov     rcx, [rsp+38h+var_10]
0x1400378cc  xor     rcx, rsp; StackCookie
0x1400378cf  call    __security_check_cookie
0x1400378d4  mov     rbx, [rsp+38h+arg_10]
0x1400378d9  mov     rsi, [rsp+38h+arg_18]
0x1400378de  add     rsp, 30h
0x1400378e2  pop     rdi
0x1400378e3  retn
0x1400378e5  mov     eax, 0C000000Dh
0x1400378ea  jmp     short loc_1400378C7
0x1400378ec  mov     rcx, cs:MpData
0x1400378f3  mov     edx, [rcx+364h]
0x1400378f9  test    edx, edx
0x1400378fb  jns     short loc_1400378B7
0x1400378fd  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140037904  nop     dword ptr [rax+rax+00h]
0x140037909  test    al, al
0x14003790b  jnz     short loc_140037910
0x14003790d  int     3; Trap to Debugger
0x14003790e  jmp     short loc_1400378B7
0x140037910  mov     ecx, 1; BugCheckCode
0x140037915  call    cs:__imp_KeBugCheck
0x140037922  lfence
0x140037925  jmp     short loc_1400378C7
```

# BaseSrvRegisterThread

- ea: `0x180005da0`
- end: `0x180005efc`
- name: `BaseSrvRegisterThread`
- size: `348`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005da0`

## import_xrefs

- `ntdll!NtClose` at `0x180005edd`
- `ntdll!NtClose` at `0x180005edd`
- `ntdll!NtDuplicateObject` at `0x180005e38`
- `ntdll!NtDuplicateObject` at `0x180005e38`
- `CSRSRV!CsrUnlockThread` at `0x180005eb7`
- `CSRSRV!CsrUnlockThread` at `0x180005eb7`
- `CSRSRV!CsrLockThreadByClientId` at `0x180005e92`
- `CSRSRV!CsrLockThreadByClientId` at `0x180005e92`
- `CSRSRV!CsrUnlockProcess` at `0x180005e73`
- `CSRSRV!CsrUnlockProcess` at `0x180005eee`
- `CSRSRV!CsrUnlockProcess` at `0x180005e73`
- `CSRSRV!CsrUnlockProcess` at `0x180005eee`
- `CSRSRV!CsrCreateThread` at `0x180005e5c`
- `CSRSRV!CsrCreateThread` at `0x180005e5c`
- `CSRSRV!CsrLockProcessByClientId` at `0x180005df6`
- `CSRSRV!CsrLockProcessByClientId` at `0x180005df6`

## pseudocode

```c
__int64 __fastcall BaseSrvRegisterThread(__int64 a1)
{
  struct _TEB *v1; // rdi
  __int128 v2; // rax
  __int64 result; // rax
  NTSTATUS v4; // ebx
  __int128 v5; // [rsp+40h] [rbp-18h] BYREF
  __int64 v6; // [rsp+60h] [rbp+8h] BYREF
  void *TargetHandle; // [rsp+70h] [rbp+18h] BYREF
  void *v8; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  v8 = 0;
  TargetHandle = 0;
  v1 = NtCurrentTeb();
  v2 = *(_OWORD *)(a1 + 72);
  v5 = v2;
  if ( *(_OWORD *)&v1->ClientId != v2 )
    return 3221225485LL;
  result = CsrLockProcessByClientId(v2, &v6);
  if ( (int)result >= 0 && v6 )
  {
    v4 = NtDuplicateObject(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           (HANDLE)0xFFFFFFFFFFFFFFFELL,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &TargetHandle,
           0x1FFFFFu,
           0,
           0);
    if ( v4 >= 0 && (v4 = CsrCreateThread(v6, TargetHandle, &v5, 0), v4 < 0) )
    {
      NtClose(TargetHandle);
      CsrUnlockProcess(v6);
    }
    else
    {
      CsrUnlockProcess(v6);
      if ( v4 >= 0 )
      {
        v4 = CsrLockThreadByClientId(*((_QWORD *)&v5 + 1), v5, &v8);
        if ( v4 >= 0 )
        {
          if ( v8 )
          {
            v1->CsrClientThread = v8;
            CsrUnlockThread(v8);
          }
        }
      }
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180005da0  mov     r11, rsp
0x180005da3  mov     [r11+10h], rbx
0x180005da7  push    rdi
0x180005da8  sub     rsp, 50h
0x180005dac  xor     ebx, ebx
0x180005dae  xorps   xmm0, xmm0
0x180005db1  movups  [rsp+58h+var_18], xmm0
0x180005db6  mov     [r11+8], rbx
0x180005dba  mov     [r11+20h], rbx
0x180005dbe  mov     [r11+18h], rbx
0x180005dc2  mov     rdi, gs:30h
0x180005dcb  mov     rax, [rcx+48h]
0x180005dcf  mov     rdx, [rcx+50h]
0x180005dd3  mov     [r11-18h], rax
0x180005dd7  mov     [r11-10h], rdx
0x180005ddb  cmp     [rdi+40h], rax
0x180005ddf  jnz     loc_180005ED1
0x180005de5  cmp     [rdi+48h], rdx
0x180005de9  jnz     loc_180005ED1
0x180005def  lea     rdx, [r11+8]
0x180005df3  mov     rcx, rax
0x180005df6  call    cs:__imp_CsrLockProcessByClientId
0x180005dfd  nop     dword ptr [rax+rax+00h]
0x180005e02  test    eax, eax
0x180005e04  js      loc_180005EC5
0x180005e0a  cmp     [rsp+58h+arg_0], rbx
0x180005e0f  jz      loc_180005EC5
0x180005e15  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x180005e1c  mov     [rsp+58h+Options], ebx; Options
0x180005e20  mov     r8, rcx; TargetProcessHandle
0x180005e23  mov     [rsp+58h+HandleAttributes], ebx; HandleAttributes
0x180005e27  lea     r9, [rsp+58h+TargetHandle]; TargetHandle
0x180005e2c  mov     [rsp+58h+DesiredAccess], 1FFFFFh; DesiredAccess
0x180005e34  lea     rdx, [rbx-2]; SourceHandle
0x180005e38  call    cs:__imp_NtDuplicateObject
0x180005e3f  nop     dword ptr [rax+rax+00h]
0x180005e44  mov     ebx, eax
0x180005e46  test    eax, eax
0x180005e48  js      short loc_180005E6E
0x180005e4a  mov     rdx, [rsp+58h+TargetHandle]
0x180005e4f  lea     r8, [rsp+58h+var_18]
0x180005e54  mov     rcx, [rsp+58h+arg_0]
0x180005e59  xor     r9d, r9d
0x180005e5c  call    cs:__imp_CsrCreateThread
0x180005e63  nop     dword ptr [rax+rax+00h]
0x180005e68  mov     ebx, eax
0x180005e6a  test    eax, eax
0x180005e6c  js      short loc_180005ED8
0x180005e6e  mov     rcx, [rsp+58h+arg_0]
0x180005e73  call    cs:__imp_CsrUnlockProcess
0x180005e7a  nop     dword ptr [rax+rax+00h]
0x180005e7f  test    ebx, ebx
0x180005e81  js      short loc_180005EC3
0x180005e83  mov     rdx, qword ptr [rsp+58h+var_18]
0x180005e88  lea     r8, [rsp+58h+arg_18]
0x180005e8d  mov     rcx, qword ptr [rsp+58h+var_18+8]
0x180005e92  call    cs:__imp_CsrLockThreadByClientId
0x180005e99  nop     dword ptr [rax+rax+00h]
0x180005e9e  mov     ebx, eax
0x180005ea0  test    eax, eax
0x180005ea2  js      short loc_180005EC3
0x180005ea4  mov     rax, [rsp+58h+arg_18]
0x180005ea9  test    rax, rax
0x180005eac  jz      short loc_180005EC3
0x180005eae  mov     [rdi+70h], rax
0x180005eb2  mov     rcx, [rsp+58h+arg_18]
0x180005eb7  call    cs:__imp_CsrUnlockThread
0x180005ebe  nop     dword ptr [rax+rax+00h]
0x180005ec3  mov     eax, ebx
0x180005ec5  mov     rbx, [rsp+58h+arg_8]
0x180005eca  add     rsp, 50h
0x180005ece  pop     rdi
0x180005ecf  retn
0x180005ed1  mov     eax, 0C000000Dh
0x180005ed6  jmp     short loc_180005EC5
0x180005ed8  mov     rcx, [rsp+58h+TargetHandle]; Handle
0x180005edd  call    cs:__imp_NtClose
0x180005ee4  nop     dword ptr [rax+rax+00h]
0x180005ee9  mov     rcx, [rsp+58h+arg_0]
0x180005eee  call    cs:__imp_CsrUnlockProcess
0x180005ef5  nop     dword ptr [rax+rax+00h]
0x180005efa  jmp     short loc_180005EC3
```

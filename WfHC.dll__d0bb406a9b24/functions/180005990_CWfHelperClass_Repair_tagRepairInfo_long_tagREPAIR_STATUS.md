# CWfHelperClass::Repair(tagRepairInfo *,long *,tagREPAIR_STATUS *)

- ea: `0x180005990`
- end: `0x180005a49`
- name: `?Repair@CWfHelperClass@@UEAAJPEAUtagRepairInfo@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, struct tagRepairInfo *, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180005990`
- `0x180006830`
- `0x180009310`
- `0x18000e010`

## string_xrefs

- `0x180005a23`: `Repair Failed. Error Code [0x%x]`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::Repair(
        CWfHelperClass *this,
        struct tagRepairInfo *a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  __int64 result; // rax
  __int64 v7; // rdx
  signed int v8; // ebx
  __int64 (__fastcall *v9)(__int64); // rax
  bool v10; // sf

  result = 0;
  *a4 = RS_REPAIRED;
  if ( *((_DWORD *)this + 43) )
    return result;
  v7 = *((_QWORD *)this + 20);
  if ( v7 )
  {
    v8 = 0;
    while ( LODWORD(g_FWDiagResolvers[2 * (int)result]) != *(_DWORD *)(v7 + 4) )
    {
      LODWORD(result) = result + 1;
      if ( (unsigned int)result >= 0xA )
        goto LABEL_12;
    }
    v9 = (__int64 (__fastcall *)(__int64))*(&funcs_180005A02 + 2 * (int)result);
    if ( v9 )
      v8 = v9(v7);
    v10 = v8 < 0;
    if ( v8 <= 0 )
      goto LABEL_13;
  }
  else
  {
    LOWORD(v8) = 87;
  }
  v8 = (unsigned __int16)v8 | 0x80070000;
LABEL_12:
  v10 = v8 < 0;
LABEL_13:
  if ( v10 )
  {
    *a4 = RS_UNREPAIRED;
    CWfHelperClass::WriteToNdfEtw(this, 2, L"Repair Failed. Error Code [0x%x]", (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005990  mov     [rsp+arg_8], rsi
0x180005995  push    rdi
0x180005996  sub     rsp, 20h
0x18000599a  xor     eax, eax
0x18000599c  mov     dword ptr [r9], 1
0x1800059a3  mov     rsi, r9
0x1800059a6  mov     rdi, rcx
0x1800059a9  cmp     [rcx+0ACh], eax
0x1800059af  jnz     loc_180005A3E
0x1800059b5  mov     rdx, [rcx+0A0h]
0x1800059bc  mov     [rsp+28h+arg_0], rbx
0x1800059c1  test    rdx, rdx
0x1800059c4  jnz     short loc_1800059CD
0x1800059c6  mov     ebx, 57h ; 'W'
0x1800059cb  jmp     short loc_180005A0D
0x1800059cd  mov     r8d, [rdx+4]
0x1800059d1  lea     r9, g_FWDiagResolvers
0x1800059d8  xor     ebx, ebx
0x1800059da  nop     word ptr [rax+rax+00h]
0x1800059e0  movsxd  rcx, eax
0x1800059e3  add     rcx, rcx
0x1800059e6  cmp     [r9+rcx*8], r8d
0x1800059ea  jz      short loc_1800059F5
0x1800059ec  inc     eax
0x1800059ee  cmp     eax, 0Ah
0x1800059f1  jb      short loc_1800059E0
0x1800059f3  jmp     short loc_180005A16
0x1800059f5  mov     rax, (funcs_180005A02 - 180015070h)[r9+rcx*8]
0x1800059fa  test    rax, rax
0x1800059fd  jz      short loc_180005A09
0x1800059ff  mov     rcx, rdx
0x180005a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a07  mov     ebx, eax
0x180005a09  test    ebx, ebx
0x180005a0b  jle     short loc_180005A18
0x180005a0d  movzx   ebx, bx
0x180005a10  or      ebx, 80070000h
0x180005a16  test    ebx, ebx
0x180005a18  jns     short loc_180005A37
0x180005a1a  mov     r9d, ebx
0x180005a1d  mov     dword ptr [rsi], 2
0x180005a23  lea     r8, aRepairFailedEr; "Repair Failed. Error Code [0x%x]"
0x180005a2a  mov     edx, 2
0x180005a2f  mov     rcx, rdi
0x180005a32  call    ?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)
0x180005a37  mov     eax, ebx
0x180005a39  mov     rbx, [rsp+28h+arg_0]
0x180005a3e  mov     rsi, [rsp+28h+arg_8]
0x180005a43  add     rsp, 20h
0x180005a47  pop     rdi
0x180005a48  retn
```

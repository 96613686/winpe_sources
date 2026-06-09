# IsolationAwareTaskDialogIndirect

- ea: `0x18000bcf4`
- end: `0x18000bde5`
- name: `IsolationAwareTaskDialogIndirect`
- size: `241`
- prototype: `signed int __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006fd8`
- `0x180007a10`

## callees

- `0x18000b9a0`
- `0x18000bb28`
- `0x18000bcf4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd81`
- `KERNEL32!DeactivateActCtx` at `0x18000bdd8`
- `KERNEL32!DeactivateActCtx` at `0x18000cea9`
- `KERNEL32!DeactivateActCtx` at `0x18000bdd8`
- `KERNEL32!DeactivateActCtx` at `0x18000cea9`

## string_xrefs

- `0x18000bd6d`: `TaskDialogIndirect`

## pseudocode

```c
signed int __fastcall IsolationAwareTaskDialogIndirect(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(_QWORD, _QWORD, _QWORD, _QWORD); // rbx
  signed int result; // eax
  FARPROC v6; // rax
  signed int LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+58h] [rbp+20h] BYREF

  v4 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))`IsolationAwareTaskDialogIndirect'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    result = GetLastError();
    if ( !result )
      result = 1359;
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( !v4 )
  {
    v6 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialogIndirect");
    v4 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1359;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    `IsolationAwareTaskDialogIndirect'::`2'::s_pfn = (__int64)v6;
  }
  LastError = v4(a1, a2, 0, 0);
LABEL_17:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return LastError;
}

```

## disassembly

```asm
0x18000bcf4  mov     rax, rsp
0x18000bcf7  mov     [rax+8], rbx
0x18000bcfb  mov     [rax+10h], rsi
0x18000bcff  mov     [rax+20h], r9
0x18000bd03  push    rdi
0x18000bd04  sub     rsp, 30h
0x18000bd08  mov     rdi, rdx
0x18000bd0b  mov     rsi, rcx
0x18000bd0e  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18000bd15  mov     qword ptr [rax+20h], 0
0x18000bd1d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bd24  jnz     short loc_18000BD68
0x18000bd26  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bd2d  jnz     short loc_18000BD68
0x18000bd2f  lea     rcx, [rax+20h]; lpCookie
0x18000bd33  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000bd38  test    eax, eax
0x18000bd3a  jnz     short loc_18000BD68
0x18000bd3c  call    cs:__imp_GetLastError
0x18000bd42  mov     ecx, 54Fh
0x18000bd47  test    eax, eax
0x18000bd49  cmovz   eax, ecx
0x18000bd4c  test    eax, eax
0x18000bd4e  jle     short loc_18000BD58
0x18000bd50  movzx   eax, ax
0x18000bd53  or      eax, 80070000h
0x18000bd58  mov     rbx, [rsp+38h+arg_0]
0x18000bd5d  mov     rsi, [rsp+38h+arg_8]
0x18000bd62  add     rsp, 30h
0x18000bd66  pop     rdi
0x18000bd67  retn
0x18000bd68  test    rbx, rbx
0x18000bd6b  jnz     short loc_18000BDA9
0x18000bd6d  lea     rcx, aTaskdialogindi; "TaskDialogIndirect"
0x18000bd74  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000bd79  mov     rbx, rax
0x18000bd7c  test    rax, rax
0x18000bd7f  jnz     short loc_18000BDA2
0x18000bd81  call    cs:__imp_GetLastError
0x18000bd87  mov     ebx, eax
0x18000bd89  mov     ecx, 54Fh
0x18000bd8e  test    eax, eax
0x18000bd90  cmovz   ebx, ecx
0x18000bd93  test    ebx, ebx
0x18000bd95  jle     short loc_18000BDBF
0x18000bd97  movzx   ebx, bx
0x18000bd9a  or      ebx, 80070000h
0x18000bda0  jmp     short loc_18000BDBF
0x18000bda2  mov     cs:?s_pfn@?1??IsolationAwareTaskDialogIndirect@@9@4P6AJPEBU_TASKDIALOGCONFIG@@PEAH11@ZEA, rax; long (*`IsolationAwareTaskDialogIndirect'::`2'::s_pfn)(_TASKDIALOGCONFIG const *,int *,int *,int *)
0x18000bda9  xor     r9d, r9d
0x18000bdac  xor     r8d, r8d
0x18000bdaf  mov     rdx, rdi
0x18000bdb2  mov     rcx, rsi
0x18000bdb5  mov     rax, rbx
0x18000bdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdbd  mov     ebx, eax
0x18000bdbf  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bdc6  jz      short loc_18000BDD1
0x18000bdc8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bdcf  jnz     short loc_18000BDDE
0x18000bdd1  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000bdd6  xor     ecx, ecx; dwFlags
0x18000bdd8  call    cs:__imp_DeactivateActCtx
0x18000bdde  mov     eax, ebx
0x18000bde0  jmp     loc_18000BD58
0x18000ce88  push    rbp
0x18000ce8a  sub     rsp, 30h
0x18000ce8e  mov     rbp, rdx
0x18000ce91  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ce98  jz      short loc_18000CEA3
0x18000ce9a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000cea1  jnz     short loc_18000CEB0
0x18000cea3  mov     rdx, [rbp+58h]; ulCookie
0x18000cea7  xor     ecx, ecx; dwFlags
0x18000cea9  call    cs:__imp_DeactivateActCtx
0x18000ceaf  nop
0x18000ceb0  add     rsp, 30h
0x18000ceb4  pop     rbp
0x18000ceb5  retn
```

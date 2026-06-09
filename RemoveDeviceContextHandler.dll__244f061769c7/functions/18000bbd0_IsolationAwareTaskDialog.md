# IsolationAwareTaskDialog

- ea: `0x18000bbd0`
- end: `0x18000bcec`
- name: `IsolationAwareTaskDialog`
- size: `284`
- prototype: `signed int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007a10`

## callees

- `0x18000b9a0`
- `0x18000bb28`
- `0x18000bbd0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc61`
- `KERNEL32!DeactivateActCtx` at `0x18000bcdf`
- `KERNEL32!DeactivateActCtx` at `0x18000ce74`
- `KERNEL32!DeactivateActCtx` at `0x18000bcdf`
- `KERNEL32!DeactivateActCtx` at `0x18000ce74`

## string_xrefs

- `0x18000bc4d`: `TaskDialog`

## pseudocode

```c
signed int __fastcall IsolationAwareTaskDialog(__int64 a1)
{
  HINSTANCE v2; // rsi
  __int64 (__fastcall *v3)(__int64, HINSTANCE, __int64); // rbx
  signed int result; // eax
  FARPROC v5; // rax
  signed int LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+78h] [rbp+20h] BYREF

  v2 = g_hinst;
  v3 = (__int64 (__fastcall *)(__int64, HINSTANCE, __int64))`IsolationAwareTaskDialog'::`2'::s_pfn;
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
  if ( !v3 )
  {
    v5 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("TaskDialog");
    v3 = (__int64 (__fastcall *)(__int64, HINSTANCE, __int64))v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1359;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_17;
    }
    `IsolationAwareTaskDialog'::`2'::s_pfn = (__int64)v5;
  }
  LastError = v3(a1, v2, 1009);
LABEL_17:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
    DeactivateActCtx(0, ulCookie);
  return LastError;
}

```

## disassembly

```asm
0x18000bbd0  mov     rax, rsp
0x18000bbd3  mov     [rax+8], rbx
0x18000bbd7  mov     [rax+10h], rsi
0x18000bbdb  mov     [rax+20h], r9
0x18000bbdf  push    rdi
0x18000bbe0  sub     rsp, 50h
0x18000bbe4  mov     rdi, rcx
0x18000bbe7  mov     rsi, cs:g_hinst
0x18000bbee  mov     rbx, cs:?s_pfn@?1??IsolationAwareTaskDialog@@9@4P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22H2PEAH@ZEA; long (*`IsolationAwareTaskDialog'::`2'::s_pfn)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,int,ushort const *,int *)
0x18000bbf5  mov     qword ptr [rax+20h], 0
0x18000bbfd  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bc04  jnz     short loc_18000BC48
0x18000bc06  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bc0d  jnz     short loc_18000BC48
0x18000bc0f  lea     rcx, [rax+20h]; lpCookie
0x18000bc13  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000bc18  test    eax, eax
0x18000bc1a  jnz     short loc_18000BC48
0x18000bc1c  call    cs:__imp_GetLastError
0x18000bc22  mov     ecx, 54Fh
0x18000bc27  test    eax, eax
0x18000bc29  cmovz   eax, ecx
0x18000bc2c  test    eax, eax
0x18000bc2e  jle     short loc_18000BC38
0x18000bc30  movzx   eax, ax
0x18000bc33  or      eax, 80070000h
0x18000bc38  mov     rbx, [rsp+58h+arg_0]
0x18000bc3d  mov     rsi, [rsp+58h+arg_8]
0x18000bc42  add     rsp, 50h
0x18000bc46  pop     rdi
0x18000bc47  retn
0x18000bc48  test    rbx, rbx
0x18000bc4b  jnz     short loc_18000BC89
0x18000bc4d  lea     rcx, aTaskdialog; "TaskDialog"
0x18000bc54  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000bc59  mov     rbx, rax
0x18000bc5c  test    rax, rax
0x18000bc5f  jnz     short loc_18000BC82
0x18000bc61  call    cs:__imp_GetLastError
0x18000bc67  mov     ebx, eax
0x18000bc69  mov     ecx, 54Fh
0x18000bc6e  test    eax, eax
0x18000bc70  cmovz   ebx, ecx
0x18000bc73  test    ebx, ebx
0x18000bc75  jle     short loc_18000BCC6
0x18000bc77  movzx   ebx, bx
0x18000bc7a  or      ebx, 80070000h
0x18000bc80  jmp     short loc_18000BCC6
0x18000bc82  mov     cs:?s_pfn@?1??IsolationAwareTaskDialog@@9@4P6AJPEAUHWND__@@PEAUHINSTANCE__@@PEBG22H2PEAH@ZEA, rax; long (*`IsolationAwareTaskDialog'::`2'::s_pfn)(HWND__ *,HINSTANCE__ *,ushort const *,ushort const *,ushort const *,int,ushort const *,int *)
0x18000bc89  mov     [rsp+58h+var_20], 0
0x18000bc92  mov     [rsp+58h+var_28], 0FFFEh
0x18000bc9b  mov     [rsp+58h+var_30], 1
0x18000bca3  mov     [rsp+58h+var_38], 0
0x18000bcac  mov     r9d, 3F2h
0x18000bcb2  lea     r8d, [r9-1]
0x18000bcb6  mov     rdx, rsi
0x18000bcb9  mov     rcx, rdi
0x18000bcbc  mov     rax, rbx
0x18000bcbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcc4  mov     ebx, eax
0x18000bcc6  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000bccd  jz      short loc_18000BCD8
0x18000bccf  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bcd6  jnz     short loc_18000BCE5
0x18000bcd8  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x18000bcdd  xor     ecx, ecx; dwFlags
0x18000bcdf  call    cs:__imp_DeactivateActCtx
0x18000bce5  mov     eax, ebx
0x18000bce7  jmp     loc_18000BC38
0x18000ce53  push    rbp
0x18000ce55  sub     rsp, 50h
0x18000ce59  mov     rbp, rdx
0x18000ce5c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000ce63  jz      short loc_18000CE6E
0x18000ce65  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ce6c  jnz     short loc_18000CE7B
0x18000ce6e  mov     rdx, [rbp+78h]; ulCookie
0x18000ce72  xor     ecx, ecx; dwFlags
0x18000ce74  call    cs:__imp_DeactivateActCtx
0x18000ce7a  nop
0x18000ce7b  add     rsp, 50h
0x18000ce7f  pop     rbp
0x18000ce80  retn
```

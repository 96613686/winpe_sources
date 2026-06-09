# GetSessionNotificationHandler(IWindowsActionDialog *,void * *)

- ea: `0x140004b48`
- end: `0x140004bf7`
- name: `?GetSessionNotificationHandler@@YAJPEAUIWindowsActionDialog@@PEAPEAX@Z`
- size: `175`
- prototype: `__int64 __fastcall(struct IWindowsActionDialog *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140004f6c`

## callees

- `0x140001460`
- `0x140004b48`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140004bb4`
- `KERNEL32!GetLastError` at `0x140004bb4`
- `KERNEL32!OpenEventW` at `0x140004ba6`
- `KERNEL32!OpenEventW` at `0x140004ba6`
- `OLEAUT32!__imp_SysFreeString` at `0x140004bd7`
- `OLEAUT32!__imp_SysFreeString` at `0x140004bd7`

## pseudocode

```c
__int64 __fastcall GetSessionNotificationHandler(struct IWindowsActionDialog *a1, void **a2)
{
  signed int v3; // ebx
  __int64 v4; // rax
  HANDLE v5; // rax
  signed int LastError; // eax
  LPCWSTR lpName; // [rsp+20h] [rbp-18h] BYREF

  v3 = -2147024809;
  if ( a1 && a2 )
  {
    *a2 = 0;
    v4 = *(_QWORD *)a1;
    lpName = 0;
    v3 = (*(__int64 (__fastcall **)(struct IWindowsActionDialog *, LPCWSTR *))(v4 + 64))(a1, &lpName);
    if ( v3 >= 0 )
    {
      v5 = OpenEventW(0x100000u, 0, lpName);
      *a2 = v5;
      if ( v5 )
      {
        v3 = 0;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    if ( lpName )
      SysFreeString((BSTR)lpName);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140004b48  mov     [rsp+arg_10], rbx
0x140004b4d  push    rdi
0x140004b4e  sub     rsp, 30h
0x140004b52  mov     rax, cs:__security_cookie
0x140004b59  xor     rax, rsp
0x140004b5c  mov     [rsp+38h+var_10], rax
0x140004b61  mov     rdi, rdx
0x140004b64  mov     ebx, 80070057h
0x140004b69  test    rcx, rcx
0x140004b6c  jz      short loc_140004BDD
0x140004b6e  test    rdx, rdx
0x140004b71  jz      short loc_140004BDD
0x140004b73  mov     qword ptr [rdx], 0
0x140004b7a  lea     rdx, [rsp+38h+lpName]
0x140004b7f  mov     rax, [rcx]
0x140004b82  mov     [rsp+38h+lpName], 0
0x140004b8b  mov     rax, [rax+40h]
0x140004b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b94  mov     ebx, eax
0x140004b96  test    eax, eax
0x140004b98  js      short loc_140004BCD
0x140004b9a  mov     r8, [rsp+38h+lpName]; lpName
0x140004b9f  xor     edx, edx; bInheritHandle
0x140004ba1  mov     ecx, 100000h; dwDesiredAccess
0x140004ba6  call    cs:__imp_OpenEventW
0x140004bac  mov     [rdi], rax
0x140004baf  test    rax, rax
0x140004bb2  jnz     short loc_140004BCB
0x140004bb4  call    cs:__imp_GetLastError
0x140004bba  mov     ebx, eax
0x140004bbc  test    eax, eax
0x140004bbe  jle     short loc_140004BCD
0x140004bc0  movzx   ebx, ax
0x140004bc3  or      ebx, 80070000h
0x140004bc9  jmp     short loc_140004BCD
0x140004bcb  xor     ebx, ebx
0x140004bcd  mov     rcx, [rsp+38h+lpName]; bstrString
0x140004bd2  test    rcx, rcx
0x140004bd5  jz      short loc_140004BDD
0x140004bd7  call    cs:__imp_SysFreeString
0x140004bdd  mov     eax, ebx
0x140004bdf  mov     rcx, [rsp+38h+var_10]
0x140004be4  xor     rcx, rsp; StackCookie
0x140004be7  call    __security_check_cookie
0x140004bec  mov     rbx, [rsp+38h+arg_10]
0x140004bf1  add     rsp, 30h
0x140004bf5  pop     rdi
0x140004bf6  retn
```

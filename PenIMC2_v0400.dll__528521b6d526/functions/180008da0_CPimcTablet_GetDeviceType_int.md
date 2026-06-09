# CPimcTablet::GetDeviceType(int *)

- ea: `0x180008da0`
- end: `0x180008ea4`
- name: `?GetDeviceType@CPimcTablet@@UEAAJPEAH@Z`
- size: `260`
- prototype: `__int64 __fastcall(CPimcTablet *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180008da0`
- `0x18000e4a0`

## import_xrefs

- `VCRUNTIME140_CLR0400!wcsstr` at `0x180008e7f`
- `VCRUNTIME140_CLR0400!wcsstr` at `0x180008e7f`
- `ole32!CoTaskMemFree` at `0x180008e91`
- `ole32!CoTaskMemFree` at `0x180008e91`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPimcTablet::GetDeviceType(CPimcTablet *this, int *a2)
{
  int v4; // ebx
  signed int v5; // edi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  int v7; // eax
  __int64 v8; // rcx
  int v10; // [rsp+58h] [rbp+38h] BYREF
  __int64 v11; // [rsp+60h] [rbp+40h] BYREF
  wchar_t *Str; // [rsp+68h] [rbp+48h] BYREF

  v4 = 0;
  Str = 0;
  v5 = a2 == 0 ? 0x80070057 : 0;
  if ( !a2 )
    goto LABEL_13;
  *a2 = 0;
  v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = 0;
    v7 = (**v6)(v6, &IID_ITablet2, &v11);
    v8 = v11;
    if ( v7 < 0 )
      v8 = 0;
    v11 = v8;
    if ( v8 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 24LL))(v8, &v10);
      if ( v5 >= 0 )
      {
        *a2 = v10;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        goto LABEL_13;
      }
    }
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v5 = (*(__int64 (__fastcall **)(CPimcTablet *, wchar_t **))(*(_QWORD *)this + 32LL))(this, &Str);
  if ( v5 >= 0 )
  {
    LOBYTE(v4) = wcsstr(Str, L"\\\\.\\DISPLAY") == 0;
    *a2 = v4;
  }
LABEL_13:
  CoTaskMemFree(Str);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008da0  push    rbp
0x180008da2  push    rbx
0x180008da3  push    rsi
0x180008da4  push    rdi
0x180008da5  push    r14
0x180008da7  mov     rbp, rsp
0x180008daa  sub     rsp, 20h
0x180008dae  mov     rsi, rdx
0x180008db1  mov     r14, rcx
0x180008db4  xor     ebx, ebx
0x180008db6  mov     [rbp+Str], rbx
0x180008dba  mov     rax, rdx
0x180008dbd  neg     rax
0x180008dc0  sbb     edi, edi
0x180008dc2  not     edi
0x180008dc4  and     edi, 80070057h
0x180008dca  test    rdx, rdx
0x180008dcd  jz      loc_180008E8D
0x180008dd3  mov     [rdx], ebx
0x180008dd5  mov     rcx, [rcx+18h]
0x180008dd9  test    rcx, rcx
0x180008ddc  jz      short loc_180008E5A
0x180008dde  mov     [rbp+arg_10], rbx
0x180008de2  mov     rax, [rcx]
0x180008de5  lea     r8, [rbp+arg_10]
0x180008de9  lea     rdx, IID_ITablet2
0x180008df0  mov     rax, [rax]
0x180008df3  call    cs:__guard_dispatch_icall_fptr
0x180008df9  mov     rcx, [rbp+arg_10]
0x180008dfd  test    eax, eax
0x180008dff  cmovs   rcx, rbx
0x180008e03  mov     [rbp+arg_10], rcx
0x180008e07  mov     rcx, [rbp+arg_10]
0x180008e0b  test    rcx, rcx
0x180008e0e  jz      short loc_180008E44
0x180008e10  mov     rax, [rcx]
0x180008e13  lea     rdx, [rbp+arg_8]
0x180008e17  mov     rax, [rax+18h]
0x180008e1b  call    cs:__guard_dispatch_icall_fptr
0x180008e21  mov     edi, eax
0x180008e23  test    eax, eax
0x180008e25  js      short loc_180008E44
0x180008e27  mov     ecx, [rbp+arg_8]
0x180008e2a  mov     [rsi], ecx
0x180008e2c  mov     rcx, [rbp+arg_10]
0x180008e30  test    rcx, rcx
0x180008e33  jz      short loc_180008E8D
0x180008e35  mov     rax, [rcx]
0x180008e38  mov     rax, [rax+10h]
0x180008e3c  call    cs:__guard_dispatch_icall_fptr
0x180008e42  jmp     short loc_180008E8D
0x180008e44  mov     rcx, [rbp+arg_10]
0x180008e48  test    rcx, rcx
0x180008e4b  jz      short loc_180008E5A
0x180008e4d  mov     rax, [rcx]
0x180008e50  mov     rax, [rax+10h]
0x180008e54  call    cs:__guard_dispatch_icall_fptr
0x180008e5a  mov     rax, [r14]
0x180008e5d  lea     rdx, [rbp+Str]
0x180008e61  mov     rcx, r14
0x180008e64  mov     rax, [rax+20h]
0x180008e68  call    cs:__guard_dispatch_icall_fptr
0x180008e6e  mov     edi, eax
0x180008e70  test    eax, eax
0x180008e72  js      short loc_180008E8D
0x180008e74  lea     rdx, aDisplay; "\\\\.\\DISPLAY"
0x180008e7b  mov     rcx, [rbp+Str]; Str
0x180008e7f  call    cs:__imp_wcsstr
0x180008e85  test    rax, rax
0x180008e88  setz    bl
0x180008e8b  mov     [rsi], ebx
0x180008e8d  mov     rcx, [rbp+Str]; pv
0x180008e91  call    cs:__imp_CoTaskMemFree
0x180008e97  mov     eax, edi
0x180008e99  add     rsp, 20h
0x180008e9d  pop     r14
0x180008e9f  pop     rdi
0x180008ea0  pop     rsi
0x180008ea1  pop     rbx
0x180008ea2  pop     rbp
0x180008ea3  retn
```

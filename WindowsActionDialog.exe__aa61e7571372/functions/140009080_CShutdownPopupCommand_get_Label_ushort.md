# CShutdownPopupCommand::get_Label(ushort * *)

- ea: `0x140009080`
- end: `0x14000918a`
- name: `?get_Label@CShutdownPopupCommand@@UEAAJPEAPEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(CShutdownPopupCommand *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001460`
- `0x1400080c8`
- `0x1400080f4`
- `0x140008e88`
- `0x140009080`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400090bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1400090bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000910f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000910f`

## string_xrefs

- `0x1400090cd`: `drivers\mobilepc\location\product\winactiondialog\lib\popupcommand.cpp`
- `0x140009151`: `drivers\mobilepc\location\product\winactiondialog\lib\popupcommand.cpp`

## pseudocode

```c
__int64 __fastcall CShutdownPopupCommand::get_Label(CShutdownPopupCommand *this, unsigned __int16 **a2)
{
  const char *v3; // r9
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rsi
  unsigned __int16 *v7; // rax
  unsigned int v8; // ebx
  unsigned __int16 **v9; // [rsp+20h] [rbp-268h]
  unsigned __int64 *v10; // [rsp+28h] [rbp-260h]
  unsigned int v11; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  *a2 = 0;
  if ( LoadStringW(*((HINSTANCE *)this + 2), *((_DWORD *)this + 11), Buffer, 260) <= 0 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x15,
             (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupcommand.cpp",
             v3);
  v5 = -1;
  do
    ++v5;
  while ( Buffer[v5] );
  v6 = v5 + 1;
  *a2 = 0;
  if ( v5 + 1 >= v5 && is_mul_ok(v6, 2u) )
  {
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v6);
    *a2 = v7;
    v8 = v7 == 0 ? 0x8007000E : 0;
    if ( v7 )
    {
      StringCchCopyNExW(v7, v5 + 1, Buffer, v5, v9, v10, v11);
      return 0;
    }
  }
  else
  {
    v8 = -2147024362;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16,
    (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupcommand.cpp",
    (const char *)v8,
    (int)v9);
  return v8;
}

```

## disassembly

```asm
0x140009080  mov     [rsp+arg_10], rbx
0x140009085  push    rbp
0x140009086  push    rsi
0x140009087  push    rdi
0x140009088  sub     rsp, 270h
0x14000908f  mov     rax, cs:__security_cookie
0x140009096  xor     rax, rsp
0x140009099  mov     [rsp+288h+var_28], rax
0x1400090a1  mov     rbx, rdx
0x1400090a4  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x1400090a9  xor     ebp, ebp
0x1400090ab  mov     r9d, 104h; cchBufferMax
0x1400090b1  mov     [rdx], rbp
0x1400090b4  mov     edx, [rcx+2Ch]; uID
0x1400090b7  mov     rcx, [rcx+10h]; hInstance
0x1400090bb  call    cs:__imp_LoadStringW
0x1400090c1  test    eax, eax
0x1400090c3  jg      short loc_1400090E1
0x1400090c5  mov     rcx, [rsp+288h]; this
0x1400090cd  lea     r8, aDriversMobilep_0; "drivers\\mobilepc\\location\\product\\w"...
0x1400090d4  lea     edx, [rbp+15h]; void *
0x1400090d7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400090dc  jmp     loc_140009167
0x1400090e1  lea     rax, [rsp+288h+Buffer]
0x1400090e6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400090ea  inc     rdi
0x1400090ed  cmp     [rax+rdi*2], bp
0x1400090f1  jnz     short loc_1400090EA
0x1400090f3  lea     rsi, [rdi+1]
0x1400090f7  mov     [rbx], rbp
0x1400090fa  cmp     rsi, rdi
0x1400090fd  jb      short loc_140009144
0x1400090ff  mov     eax, 2
0x140009104  mul     rsi
0x140009107  test    rdx, rdx
0x14000910a  jnz     short loc_140009144
0x14000910c  mov     rcx, rax; cb
0x14000910f  call    cs:__imp_CoTaskMemAlloc
0x140009115  mov     [rbx], rax
0x140009118  mov     rcx, rax
0x14000911b  neg     rcx
0x14000911e  sbb     ebx, ebx
0x140009120  not     ebx
0x140009122  and     ebx, 8007000Eh
0x140009128  test    rax, rax
0x14000912b  jz      short loc_140009149
0x14000912d  mov     r9, rdi; unsigned __int64
0x140009130  lea     r8, [rsp+288h+Buffer]; unsigned __int16 *
0x140009135  mov     rdx, rsi; unsigned __int64
0x140009138  mov     rcx, rax; unsigned __int16 *
0x14000913b  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x140009140  xor     eax, eax
0x140009142  jmp     short loc_140009167
0x140009144  mov     ebx, 80070216h
0x140009149  mov     rcx, [rsp+288h]; this
0x140009151  lea     r8, aDriversMobilep_0; "drivers\\mobilepc\\location\\product\\w"...
0x140009158  mov     r9d, ebx; char *
0x14000915b  mov     edx, 16h; void *
0x140009160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009165  mov     eax, ebx
0x140009167  mov     rcx, [rsp+288h+var_28]
0x14000916f  xor     rcx, rsp; StackCookie
0x140009172  call    __security_check_cookie
0x140009177  mov     rbx, [rsp+288h+arg_10]
0x14000917f  add     rsp, 270h
0x140009186  pop     rdi
0x140009187  pop     rsi
0x140009188  pop     rbp
0x140009189  retn
```

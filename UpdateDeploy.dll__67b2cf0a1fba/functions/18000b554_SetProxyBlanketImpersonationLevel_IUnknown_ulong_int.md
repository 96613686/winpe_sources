# SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)

- ea: `0x18000b554`
- end: `0x18000b734`
- name: `?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z`
- size: `480`
- prototype: `__int64 __fastcall(struct IUnknown *, unsigned int, int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006be0`
- `0x180017850`
- `0x180018790`

## callees

- `0x180003180`
- `0x18000b554`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b6e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b60d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b6e9`

## string_xrefs

- `0x18000b6d0`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SetProxyBlanketImpersonationLevel(struct IUnknown *a1, __int64 a2, int *a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  LPVOID *p_pv; // [rsp+28h] [rbp-19h]
  LPVOID pv; // [rsp+68h] [rbp+27h] BYREF
  int v13; // [rsp+70h] [rbp+2Fh]
  unsigned int v14; // [rsp+74h] [rbp+33h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+37h] BYREF
  __int64 v16; // [rsp+80h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A0h] [rbp+5Fh]

  v16 = 0;
  pv = 0;
  v15 = 0;
  v14 = 0;
  v13 = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    v5 = 27;
LABEL_6:
    v7 = v4;
    v8 = v5;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)v7,
      (int)p_pv);
    goto LABEL_14;
  }
  v6 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_0000013d_0000_0000_c000_000000000046,
         &v16);
  v4 = v6;
  if ( v6 >= 0 )
  {
    p_pv = &pv;
    v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, unsigned int *, unsigned int *))(*(_QWORD *)v16 + 24LL))(
           v16,
           a1,
           &v15,
           &v14);
    v4 = v9;
    if ( v9 >= 0 )
    {
      LODWORD(p_pv) = (_DWORD)pv;
      v9 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, _QWORD, _QWORD))(*(_QWORD *)v16 + 32LL))(
             v16,
             a1,
             v15,
             v14);
      v4 = v9;
      if ( v9 >= 0 )
        goto LABEL_13;
      v8 = 69;
    }
    else
    {
      v8 = 55;
    }
    v7 = (unsigned int)v9;
    goto LABEL_12;
  }
  if ( v6 != -2147467262 )
  {
    v5 = 32;
    goto LABEL_6;
  }
LABEL_13:
  v4 = 0;
LABEL_14:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return v4;
}

```

## disassembly

```asm
0x18000b554  mov     rax, rsp
0x18000b557  mov     [rax+10h], rbx
0x18000b55b  mov     [rax+18h], rsi
0x18000b55f  mov     [rax+20h], rdi
0x18000b563  push    rbp
0x18000b564  lea     rbp, [rax-5Fh]
0x18000b568  sub     rsp, 90h
0x18000b56f  mov     rax, cs:__security_cookie
0x18000b576  xor     rax, rsp
0x18000b579  mov     [rbp+57h+var_10], rax
0x18000b57d  mov     rdi, rcx
0x18000b580  mov     [rbp+57h+var_40], 0
0x18000b588  mov     [rbp+57h+var_18], 0
0x18000b590  mov     [rbp+57h+pv], 0
0x18000b598  mov     [rbp+57h+var_20], 0
0x18000b59f  mov     [rbp+57h+var_24], 0
0x18000b5a6  mov     [rbp+57h+var_28], 0
0x18000b5ad  mov     [rbp+57h+var_38], 0
0x18000b5b4  test    rcx, rcx
0x18000b5b7  jnz     short loc_18000B5C3
0x18000b5b9  mov     ebx, 80004003h
0x18000b5be  lea     eax, [rcx+1Bh]
0x18000b5c1  jmp     short loc_18000B5EF
0x18000b5c3  mov     rax, [rcx]
0x18000b5c6  lea     r8, [rbp+57h+var_18]
0x18000b5ca  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x18000b5d1  mov     rax, [rax]
0x18000b5d4  call    _guard_dispatch_icall
0x18000b5d9  mov     ebx, eax
0x18000b5db  test    eax, eax
0x18000b5dd  jns     short loc_18000B5F9
0x18000b5df  cmp     eax, 80004002h
0x18000b5e4  jz      loc_18000B6DE
0x18000b5ea  mov     eax, 20h ; ' '
0x18000b5ef  mov     r9d, ebx
0x18000b5f2  mov     edx, eax
0x18000b5f4  jmp     loc_18000B6CC
0x18000b5f9  mov     rbx, [rbp+57h+var_18]
0x18000b5fd  mov     rax, [rbx]
0x18000b600  mov     rsi, [rax+18h]
0x18000b604  mov     rcx, [rbp+57h+pv]; pv
0x18000b608  test    rcx, rcx
0x18000b60b  jz      short loc_18000B61B
0x18000b60d  call    cs:__imp_CoTaskMemFree
0x18000b613  mov     [rbp+57h+pv], 0
0x18000b61b  lea     rax, [rbp+57h+var_38]
0x18000b61f  mov     [rsp+90h+var_50], rax
0x18000b624  lea     rax, [rbp+57h+var_40]
0x18000b628  mov     [rsp+90h+var_58], rax
0x18000b62d  mov     [rsp+90h+var_60], 0
0x18000b636  lea     rax, [rbp+57h+var_28]
0x18000b63a  mov     [rsp+90h+var_68], rax
0x18000b63f  lea     rax, [rbp+57h+pv]
0x18000b643  mov     qword ptr [rsp+90h+var_70], rax
0x18000b648  lea     r9, [rbp+57h+var_24]
0x18000b64c  lea     r8, [rbp+57h+var_20]
0x18000b650  mov     rdx, rdi
0x18000b653  mov     rcx, rbx
0x18000b656  mov     rax, rsi
0x18000b659  call    _guard_dispatch_icall
0x18000b65e  mov     ebx, eax
0x18000b660  test    eax, eax
0x18000b662  jns     short loc_18000B66B
0x18000b664  mov     edx, 37h ; '7'
0x18000b669  jmp     short loc_18000B6C9
0x18000b66b  mov     r8d, [rbp+57h+var_38]
0x18000b66f  and     r8d, 0FFFFFFBFh
0x18000b673  or      r8d, 20h
0x18000b677  mov     [rbp+57h+var_38], r8d
0x18000b67b  mov     r10, [rbp+57h+var_40]
0x18000b67f  mov     r11d, [rbp+57h+var_28]
0x18000b683  mov     rbx, [rbp+57h+pv]
0x18000b687  mov     rcx, [rbp+57h+var_18]
0x18000b68b  mov     rax, [rcx]
0x18000b68e  mov     dword ptr [rsp+90h+var_50], r8d
0x18000b693  mov     [rsp+90h+var_58], r10
0x18000b698  mov     dword ptr [rsp+90h+var_60], 2
0x18000b6a0  mov     dword ptr [rsp+90h+var_68], r11d
0x18000b6a5  mov     qword ptr [rsp+90h+var_70], rbx; int
0x18000b6aa  mov     r9d, [rbp+57h+var_24]
0x18000b6ae  mov     r8d, [rbp+57h+var_20]
0x18000b6b2  mov     rdx, rdi
0x18000b6b5  mov     rax, [rax+20h]
0x18000b6b9  call    _guard_dispatch_icall
0x18000b6be  mov     ebx, eax
0x18000b6c0  test    eax, eax
0x18000b6c2  jns     short loc_18000B6DE
0x18000b6c4  mov     edx, 45h ; 'E'; void *
0x18000b6c9  mov     r9d, eax; char *
0x18000b6cc  mov     rcx, [rbp+5Fh]; this
0x18000b6d0  lea     r8, aCW1SSrcClientL_31; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000b6d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b6dc  jmp     short loc_18000B6E0
0x18000b6de  xor     ebx, ebx
0x18000b6e0  mov     rcx, [rbp+57h+pv]; pv
0x18000b6e4  test    rcx, rcx
0x18000b6e7  jz      short loc_18000B6F7
0x18000b6e9  call    cs:__imp_CoTaskMemFree
0x18000b6ef  mov     [rbp+57h+pv], 0
0x18000b6f7  mov     rcx, [rbp+57h+var_18]
0x18000b6fb  test    rcx, rcx
0x18000b6fe  jz      short loc_18000B70D
0x18000b700  mov     rdx, [rcx]
0x18000b703  mov     rax, [rdx+10h]
0x18000b707  call    _guard_dispatch_icall
0x18000b70c  nop
0x18000b70d  mov     eax, ebx
0x18000b70f  mov     rcx, [rbp+57h+var_10]
0x18000b713  xor     rcx, rsp; StackCookie
0x18000b716  call    __security_check_cookie
0x18000b71b  lea     r11, [rsp+90h+var_s0]
0x18000b723  mov     rbx, [r11+18h]
0x18000b727  mov     rsi, [r11+20h]
0x18000b72b  mov     rdi, [r11+28h]
0x18000b72f  mov     rsp, r11
0x18000b732  pop     rbp
0x18000b733  retn
```

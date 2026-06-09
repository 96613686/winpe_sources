# SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,uint,uint,_SHELLDETAILS *)

- ea: `0x180016fbc`
- end: `0x180017122`
- name: `?SHGetDetailsOfInfo@@YAJPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@IIPEAU_SHELLDETAILS@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(HINSTANCE, const struct COLUMN_INFO *, unsigned int, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013a24`

## callees

- `0x180016fbc`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `SHCORE!SHStrDupW` at `0x18001702e`
- `SHCORE!SHStrDupW` at `0x1800170b5`
- `SHCORE!SHStrDupW` at `0x1800170ee`
- `SHCORE!SHStrDupW` at `0x18001702e`
- `SHCORE!SHStrDupW` at `0x1800170b5`
- `SHCORE!SHStrDupW` at `0x1800170ee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001701f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001701f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017062`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017062`

## pseudocode

```c
__int64 __fastcall SHGetDetailsOfInfo(
        HINSTANCE a1,
        const struct COLUMN_INFO *a2,
        unsigned int a3,
        unsigned int a4,
        struct _SHELLDETAILS *a5)
{
  __int64 v6; // rsi
  UINT v7; // edx
  HRESULT v8; // ebx
  LPVOID ppv; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

  if ( a4 >= a3 )
    return (unsigned int)-2147467263;
  v6 = 32LL * a4;
  a5->fmt = *(_DWORD *)((char *)a2 + v6 + 12);
  a5->cxChar = *(_DWORD *)((char *)a2 + v6 + 16);
  v7 = *(_DWORD *)((char *)a2 + v6 + 24);
  if ( v7 )
  {
    a5->str.uType = 0;
    LoadStringW(a1, v7, Buffer, 260);
    v8 = SHStrDupW(Buffer, &a5->str.pOleStr);
    goto LABEL_8;
  }
  ppv = 0;
  v8 = CoCreateInstance(&CLSID_PropertiesUI, 0, 1u, &GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66, &ppv);
  if ( v8 >= 0 )
  {
    _mm_lfence();
    v8 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, WCHAR *, int))(*(_QWORD *)ppv + 40LL))(
           ppv,
           *(_QWORD *)((char *)a2 + v6),
           *(unsigned int *)(*(_QWORD *)((char *)a2 + v6) + 16LL),
           0,
           Buffer,
           128);
    if ( v8 >= 0 )
    {
      a5->str.uType = 0;
      v8 = SHStrDupW(Buffer, &a5->str.pOleStr);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_8:
    if ( v8 >= 0 )
      return (unsigned int)v8;
  }
  if ( (*(_DWORD *)((_BYTE *)a2 + v6 + 20) & 0x100) != 0 )
  {
    a5->str.uType = 0;
    return (unsigned int)SHStrDupW(&WindowName, &a5->str.pOleStr);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016fbc  mov     [rsp+arg_10], rbx
0x180016fc1  push    rbp
0x180016fc2  push    rsi
0x180016fc3  push    rdi
0x180016fc4  sub     rsp, 270h
0x180016fcb  mov     rax, cs:__security_cookie
0x180016fd2  xor     rax, rsp
0x180016fd5  mov     [rsp+288h+var_28], rax
0x180016fdd  mov     rdi, [rsp+288h+arg_20]
0x180016fe5  mov     rbp, rdx
0x180016fe8  cmp     r9d, r8d
0x180016feb  jnb     loc_1800170F8
0x180016ff1  mov     esi, r9d
0x180016ff4  shl     rsi, 5
0x180016ff8  mov     eax, [rsi+rdx+0Ch]
0x180016ffc  mov     [rdi], eax
0x180016ffe  mov     eax, [rsi+rdx+10h]
0x180017002  mov     [rdi+4], eax
0x180017005  mov     edx, [rsi+rdx+18h]; uID
0x180017009  test    edx, edx
0x18001700b  jz      short loc_18001703B
0x18001700d  mov     r9d, 104h; cchBufferMax
0x180017013  mov     dword ptr [rdi+8], 0
0x18001701a  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18001701f  call    cs:__imp_LoadStringW
0x180017025  lea     rdx, [rdi+10h]; ppwsz
0x180017029  lea     rcx, [rsp+288h+Buffer]; psz
0x18001702e  call    cs:__imp_SHStrDupW
0x180017034  mov     ebx, eax
0x180017036  jmp     loc_1800170CE
0x18001703b  xor     edx, edx; pUnkOuter
0x18001703d  mov     [rsp+288h+var_248], 0
0x180017046  lea     rax, [rsp+288h+var_248]
0x18001704b  lea     r9, _GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66; riid
0x180017052  mov     [rsp+288h+ppv], rax; ppv
0x180017057  lea     rcx, CLSID_PropertiesUI; rclsid
0x18001705e  lea     r8d, [rdx+1]; dwClsContext
0x180017062  call    cs:__imp_CoCreateInstance
0x180017068  mov     ebx, eax
0x18001706a  test    eax, eax
0x18001706c  js      short loc_1800170D2
0x18001706e  lfence
0x180017071  mov     rcx, [rsp+288h+var_248]
0x180017076  lea     r8, [rsp+288h+Buffer]
0x18001707b  mov     rdx, [rsi+rbp]
0x18001707f  xor     r9d, r9d
0x180017082  mov     [rsp+288h+var_260], 80h
0x18001708a  mov     [rsp+288h+ppv], r8
0x18001708f  mov     rax, [rcx]
0x180017092  mov     r8d, [rdx+10h]
0x180017096  mov     rax, [rax+28h]
0x18001709a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001709f  mov     ebx, eax
0x1800170a1  test    eax, eax
0x1800170a3  js      short loc_1800170BD
0x1800170a5  lea     rdx, [rdi+10h]; ppwsz
0x1800170a9  mov     dword ptr [rdi+8], 0
0x1800170b0  lea     rcx, [rsp+288h+Buffer]; psz
0x1800170b5  call    cs:__imp_SHStrDupW
0x1800170bb  mov     ebx, eax
0x1800170bd  mov     rcx, [rsp+288h+var_248]
0x1800170c2  mov     rax, [rcx]
0x1800170c5  mov     rax, [rax+10h]
0x1800170c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ce  test    ebx, ebx
0x1800170d0  jns     short loc_1800170FD
0x1800170d2  test    dword ptr [rsi+rbp+14h], 100h
0x1800170da  jz      short loc_1800170FD
0x1800170dc  lea     rdx, [rdi+10h]; ppwsz
0x1800170e0  mov     dword ptr [rdi+8], 0
0x1800170e7  lea     rcx, WindowName; psz
0x1800170ee  call    cs:__imp_SHStrDupW
0x1800170f4  mov     ebx, eax
0x1800170f6  jmp     short loc_1800170FD
0x1800170f8  mov     ebx, 80004001h
0x1800170fd  mov     eax, ebx
0x1800170ff  mov     rcx, [rsp+288h+var_28]
0x180017107  xor     rcx, rsp; StackCookie
0x18001710a  call    __security_check_cookie
0x18001710f  mov     rbx, [rsp+288h+arg_10]
0x180017117  add     rsp, 270h
0x18001711e  pop     rdi
0x18001711f  pop     rsi
0x180017120  pop     rbp
0x180017121  retn
```

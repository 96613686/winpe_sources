# SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,uint,uint,_SHELLDETAILS *)

- ea: `0x18003eea0`
- end: `0x18003f006`
- name: `?SHGetDetailsOfInfo@@YAJPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@IIPEAU_SHELLDETAILS@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(HINSTANCE, const struct COLUMN_INFO *, unsigned int, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ecb0`

## callees

- `0x18003eea0`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18003ef12`
- `SHLWAPI!SHStrDupW` at `0x18003ef99`
- `SHLWAPI!SHStrDupW` at `0x18003efd2`
- `SHLWAPI!SHStrDupW` at `0x18003ef12`
- `SHLWAPI!SHStrDupW` at `0x18003ef99`
- `SHLWAPI!SHStrDupW` at `0x18003efd2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003ef03`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003ef03`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ef46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003ef46`

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
    return (unsigned int)SHStrDupW(&String2, &a5->str.pOleStr);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003eea0  mov     [rsp+arg_10], rbx
0x18003eea5  push    rbp
0x18003eea6  push    rsi
0x18003eea7  push    rdi
0x18003eea8  sub     rsp, 270h
0x18003eeaf  mov     rax, cs:__security_cookie
0x18003eeb6  xor     rax, rsp
0x18003eeb9  mov     [rsp+288h+var_28], rax
0x18003eec1  mov     rdi, [rsp+288h+arg_20]
0x18003eec9  mov     rbp, rdx
0x18003eecc  cmp     r9d, r8d
0x18003eecf  jnb     loc_18003EFDC
0x18003eed5  mov     esi, r9d
0x18003eed8  shl     rsi, 5
0x18003eedc  mov     eax, [rsi+rdx+0Ch]
0x18003eee0  mov     [rdi], eax
0x18003eee2  mov     eax, [rsi+rdx+10h]
0x18003eee6  mov     [rdi+4], eax
0x18003eee9  mov     edx, [rsi+rdx+18h]; uID
0x18003eeed  test    edx, edx
0x18003eeef  jz      short loc_18003EF1F
0x18003eef1  mov     r9d, 104h; cchBufferMax
0x18003eef7  mov     dword ptr [rdi+8], 0
0x18003eefe  lea     r8, [rsp+288h+Buffer]; lpBuffer
0x18003ef03  call    cs:__imp_LoadStringW
0x18003ef09  lea     rdx, [rdi+10h]; ppwsz
0x18003ef0d  lea     rcx, [rsp+288h+Buffer]; psz
0x18003ef12  call    cs:__imp_SHStrDupW
0x18003ef18  mov     ebx, eax
0x18003ef1a  jmp     loc_18003EFB2
0x18003ef1f  xor     edx, edx; pUnkOuter
0x18003ef21  mov     [rsp+288h+var_248], 0
0x18003ef2a  lea     rax, [rsp+288h+var_248]
0x18003ef2f  lea     r9, _GUID_757a7d9f_919a_4118_99d7_dbb208c8cc66; riid
0x18003ef36  mov     [rsp+288h+ppv], rax; ppv
0x18003ef3b  lea     rcx, CLSID_PropertiesUI; rclsid
0x18003ef42  lea     r8d, [rdx+1]; dwClsContext
0x18003ef46  call    cs:__imp_CoCreateInstance
0x18003ef4c  mov     ebx, eax
0x18003ef4e  test    eax, eax
0x18003ef50  js      short loc_18003EFB6
0x18003ef52  lfence
0x18003ef55  mov     rcx, [rsp+288h+var_248]
0x18003ef5a  lea     r8, [rsp+288h+Buffer]
0x18003ef5f  mov     rdx, [rsi+rbp]
0x18003ef63  xor     r9d, r9d
0x18003ef66  mov     [rsp+288h+var_260], 80h
0x18003ef6e  mov     [rsp+288h+ppv], r8
0x18003ef73  mov     rax, [rcx]
0x18003ef76  mov     r8d, [rdx+10h]
0x18003ef7a  mov     rax, [rax+28h]
0x18003ef7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef83  mov     ebx, eax
0x18003ef85  test    eax, eax
0x18003ef87  js      short loc_18003EFA1
0x18003ef89  lea     rdx, [rdi+10h]; ppwsz
0x18003ef8d  mov     dword ptr [rdi+8], 0
0x18003ef94  lea     rcx, [rsp+288h+Buffer]; psz
0x18003ef99  call    cs:__imp_SHStrDupW
0x18003ef9f  mov     ebx, eax
0x18003efa1  mov     rcx, [rsp+288h+var_248]
0x18003efa6  mov     rax, [rcx]
0x18003efa9  mov     rax, [rax+10h]
0x18003efad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003efb2  test    ebx, ebx
0x18003efb4  jns     short loc_18003EFE1
0x18003efb6  test    dword ptr [rsi+rbp+14h], 100h
0x18003efbe  jz      short loc_18003EFE1
0x18003efc0  lea     rdx, [rdi+10h]; ppwsz
0x18003efc4  mov     dword ptr [rdi+8], 0
0x18003efcb  lea     rcx, String2; psz
0x18003efd2  call    cs:__imp_SHStrDupW
0x18003efd8  mov     ebx, eax
0x18003efda  jmp     short loc_18003EFE1
0x18003efdc  mov     ebx, 80004001h
0x18003efe1  mov     eax, ebx
0x18003efe3  mov     rcx, [rsp+288h+var_28]
0x18003efeb  xor     rcx, rsp; StackCookie
0x18003efee  call    __security_check_cookie
0x18003eff3  mov     rbx, [rsp+288h+arg_10]
0x18003effb  add     rsp, 270h
0x18003f002  pop     rdi
0x18003f003  pop     rsi
0x18003f004  pop     rbp
0x18003f005  retn
```

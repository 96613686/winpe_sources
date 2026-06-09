# DMProcessConfigXML

- ea: `0x180006260`
- end: `0x180006381`
- name: `DMProcessConfigXML`
- size: `289`
- prototype: `__int64 __fastcall(__int64, BSTR *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005224`
- `0x180006260`
- `0x180006390`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006368`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006357`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006368`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006370`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006370`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800062c1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800062c1`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800062f6`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x1800062f6`

## string_xrefs

- `0x180006309`: `OMADM::TargetedUserSID`
- `0x18000629a`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x18000633f`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`

## pseudocode

```c
__int64 __fastcall DMProcessConfigXML(__int64 a1, BSTR *a2)
{
  __int64 v4; // rdx
  unsigned int v5; // ebx
  int CurrentUserSid; // eax
  __int64 v7; // rdx
  const wchar_t *v9; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+28h] [rbp-20h]
  HLOCAL v11; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  HLOCAL hMem; // [rsp+70h] [rbp+28h] BYREF

  v9 = 0;
  v11 = 0;
  v10 = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v4 = 185;
      goto LABEL_3;
    }
    *a2 = 0;
    v5 = CoInitializeEx(0, 0);
    if ( (v5 & 0x80000000) != 0 )
    {
      v4 = 189;
      goto LABEL_4;
    }
    hMem = 0;
    v9 = L"OMADM::AccountID";
    *(_QWORD *)&v10 = L"2648BF76-DA4B-409A-BFFA-6AF111C298A5";
    CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)&hMem);
    v5 = CurrentUserSid;
    if ( CurrentUserSid >= 0 )
    {
      *((_QWORD *)&v10 + 1) = L"OMADM::TargetedUserSID";
      v11 = hMem;
      CurrentUserSid = MdmProcessConfigXmlWithAttributes(a1, 2u, (OLECHAR *)&v9, a2);
      v5 = CurrentUserSid;
      if ( CurrentUserSid >= 0 )
      {
        if ( hMem )
          LocalFree(hMem);
        v5 = 0;
        goto LABEL_18;
      }
      v7 = 214;
    }
    else
    {
      v7 = 205;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      (int)v9);
    if ( hMem )
      LocalFree(hMem);
LABEL_18:
    CoUninitialize();
    return v5;
  }
  v4 = 184;
LABEL_3:
  v5 = -2147024809;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
    (const char *)v5,
    (int)v9);
  return v5;
}

```

## disassembly

```asm
0x180006260  push    rbp
0x180006262  push    rbx
0x180006263  push    rsi
0x180006264  push    rdi
0x180006265  mov     rbp, rsp
0x180006268  sub     rsp, 48h
0x18000626c  xor     eax, eax
0x18000626e  mov     [rbp+var_28], 0
0x180006276  mov     [rbp+var_10], rax
0x18000627a  xorps   xmm0, xmm0
0x18000627d  mov     rdi, rdx
0x180006280  mov     rsi, rcx
0x180006283  movups  [rbp+var_20], xmm0
0x180006287  test    rcx, rcx
0x18000628a  jnz     short loc_1800062AE
0x18000628c  mov     edx, 0B8h; void *
0x180006291  mov     ebx, 80070057h
0x180006296  mov     rcx, [rbp+20h]; this
0x18000629a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x1800062a1  mov     r9d, ebx; char *
0x1800062a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062a9  jmp     loc_180006376
0x1800062ae  test    rdi, rdi
0x1800062b1  jnz     short loc_1800062BA
0x1800062b3  mov     edx, 0B9h
0x1800062b8  jmp     short loc_180006291
0x1800062ba  mov     [rdx], rax
0x1800062bd  xor     ecx, ecx; pvReserved
0x1800062bf  xor     edx, edx; dwCoInit
0x1800062c1  call    cs:__imp_CoInitializeEx
0x1800062c7  mov     ebx, eax
0x1800062c9  test    eax, eax
0x1800062cb  jns     short loc_1800062D4
0x1800062cd  mov     edx, 0BDh
0x1800062d2  jmp     short loc_180006296
0x1800062d4  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x1800062db  mov     [rbp+hMem], 0
0x1800062e3  mov     [rbp+var_28], rax
0x1800062e7  lea     rcx, [rbp+hMem]
0x1800062eb  lea     rax, a2648bf76Da4b40; "2648BF76-DA4B-409A-BFFA-6AF111C298A5"
0x1800062f2  mov     qword ptr [rbp+var_20], rax
0x1800062f6  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x1800062fc  mov     ebx, eax
0x1800062fe  test    eax, eax
0x180006300  jns     short loc_180006309
0x180006302  mov     edx, 0CDh
0x180006307  jmp     short loc_18000633B
0x180006309  lea     rax, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180006310  mov     r9, rdi
0x180006313  mov     qword ptr [rbp+var_20+8], rax
0x180006317  lea     r8, [rbp+var_28]
0x18000631b  mov     rax, [rbp+hMem]
0x18000631f  mov     edx, 2
0x180006324  mov     rcx, rsi
0x180006327  mov     [rbp+var_10], rax
0x18000632b  call    MdmProcessConfigXmlWithAttributes
0x180006330  mov     ebx, eax
0x180006332  test    eax, eax
0x180006334  jns     short loc_18000635F
0x180006336  mov     edx, 0D6h; void *
0x18000633b  mov     rcx, [rbp+20h]; this
0x18000633f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x180006346  mov     r9d, eax; char *
0x180006349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000634e  mov     rcx, [rbp+hMem]; hMem
0x180006352  test    rcx, rcx
0x180006355  jz      short loc_180006370
0x180006357  call    cs:__imp_LocalFree
0x18000635d  jmp     short loc_180006370
0x18000635f  mov     rcx, [rbp+hMem]; hMem
0x180006363  test    rcx, rcx
0x180006366  jz      short loc_18000636E
0x180006368  call    cs:__imp_LocalFree
0x18000636e  xor     ebx, ebx
0x180006370  call    cs:__imp_CoUninitialize
0x180006376  mov     eax, ebx
0x180006378  add     rsp, 48h
0x18000637c  pop     rdi
0x18000637d  pop     rsi
0x18000637e  pop     rbx
0x18000637f  pop     rbp
0x180006380  retn
```

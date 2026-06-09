# CInkStorage::WriteDataToSafeArray(ulong,uchar *,tagVARIANT *)

- ea: `0x180059504`
- end: `0x1800595dc`
- name: `?WriteDataToSafeArray@CInkStorage@@QEAAJKPEAEPEAUtagVARIANT@@@Z`
- size: `216`
- prototype: `int(CInkStorage *__hidden this, unsigned int, unsigned __int8 *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180058c44`
- `0x1800593f8`

## callees

- `0x18001332c`
- `0x180059504`
- `0x1800f85e8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800595c1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800595c1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005956c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005956c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800595b6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800595b6`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005952d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18005952d`

## pseudocode

```c
__int64 __fastcall CInkStorage::WriteDataToSafeArray(
        CInkStorage *this,
        ULONG a2,
        unsigned __int8 *a3,
        struct tagVARIANT *a4)
{
  size_t v5; // rbp
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rbx
  HRESULT v10; // eax
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *ppvData; // [rsp+40h] [rbp+8h] BYREF

  ppvData = this;
  v5 = a2;
  Vector = SafeArrayCreateVector(0x11u, 0, a2);
  v8 = Vector;
  if ( Vector )
  {
    ppvData = 0;
    v10 = SafeArrayAccessData(Vector, &ppvData);
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( ppvData )
      {
        memcpy_0(ppvData, a3, v5);
        a4->vt = 8209;
        a4->llVal = (LONGLONG)v8;
        SafeArrayUnaccessData(v8);
      }
      else
      {
        SafeArrayDestroy(v8);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\inkstorage.cpp",
        (const char *)(unsigned int)v10,
        v12);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\inkstorage.cpp",
      (const char *)0x8007000ELL,
      v12);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180059504  mov     [rsp+arg_8], rbx
0x180059509  mov     [rsp+arg_10], rbp
0x18005950e  mov     [rsp+ppvData], rcx
0x180059513  push    rsi
0x180059514  push    rdi
0x180059515  push    r14; int
0x180059517  sub     rsp, 20h
0x18005951b  mov     r14, r8
0x18005951e  mov     ebp, edx
0x180059520  mov     r8d, edx; cElements
0x180059523  mov     ecx, 11h; vt
0x180059528  xor     edx, edx; lLbound
0x18005952a  mov     rsi, r9
0x18005952d  call    cs:__imp_SafeArrayCreateVector
0x180059533  mov     rbx, rax
0x180059536  test    rax, rax
0x180059539  jnz     short loc_18005955B
0x18005953b  mov     rcx, [rsp+38h]; this
0x180059540  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180059547  mov     ebx, 8007000Eh
0x18005954c  lea     edx, [rax+1Ch]; void *
0x18005954f  mov     r9d, ebx; char *
0x180059552  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059557  mov     eax, ebx
0x180059559  jmp     short loc_1800595C9
0x18005955b  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180059560  mov     [rsp+38h+ppvData], 0
0x180059569  mov     rcx, rbx; psa
0x18005956c  call    cs:__imp_SafeArrayAccessData
0x180059572  mov     edi, eax
0x180059574  test    eax, eax
0x180059576  jns     short loc_180059595
0x180059578  mov     rcx, [rsp+38h]; this
0x18005957d  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180059584  mov     r9d, eax; char *
0x180059587  mov     edx, 1Fh; void *
0x18005958c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059591  mov     eax, edi
0x180059593  jmp     short loc_1800595C9
0x180059595  mov     rcx, [rsp+38h+ppvData]; void *
0x18005959a  test    rcx, rcx
0x18005959d  jz      short loc_1800595BE
0x18005959f  mov     r8, rbp; Size
0x1800595a2  mov     rdx, r14; Src
0x1800595a5  call    memcpy_0
0x1800595aa  mov     rcx, rbx; psa
0x1800595ad  mov     word ptr [rsi], 2011h
0x1800595b2  mov     [rsi+8], rbx
0x1800595b6  call    cs:__imp_SafeArrayUnaccessData
0x1800595bc  jmp     short loc_1800595C7
0x1800595be  mov     rcx, rbx; psa
0x1800595c1  call    cs:__imp_SafeArrayDestroy
0x1800595c7  xor     eax, eax
0x1800595c9  mov     rbx, [rsp+38h+arg_8]
0x1800595ce  mov     rbp, [rsp+38h+arg_10]
0x1800595d3  add     rsp, 20h
0x1800595d7  pop     r14
0x1800595d9  pop     rdi
0x1800595da  pop     rsi
0x1800595db  retn
```

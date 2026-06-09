# GetRootPath(CServerContext *,ushort *,ulong)

- ea: `0x180023cdc`
- end: `0x180023ddd`
- name: `?GetRootPath@@YAJPEAVCServerContext@@PEAGK@Z`
- size: `257`
- prototype: `__int64 __fastcall(const unsigned __int16 **, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180021dd0`
- `0x180022940`
- `0x180023330`
- `0x18002371c`

## callees

- `0x180008f58`
- `0x18001d130`
- `0x18002350c`
- `0x180023cdc`

## import_xrefs

- `adsldpc!ADSIGetObjectAttributes` at `0x180023d69`
- `adsldpc!ADSIGetObjectAttributes` at `0x180023d69`
- `adsldpc!ADSICloseDSObject` at `0x180023dbe`
- `adsldpc!ADSICloseDSObject` at `0x180023dbe`
- `adsldpc!FreeADsMem` at `0x180023dcd`
- `adsldpc!FreeADsMem` at `0x180023dcd`

## pseudocode

```c
__int64 __fastcall GetRootPath(const unsigned __int16 **a1, unsigned __int16 *a2)
{
  bool v3; // zf
  unsigned int v5; // eax
  __int64 result; // rax
  int *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  const wchar_t *v10; // [rsp+30h] [rbp-10h] BYREF
  void *v11; // [rsp+68h] [rbp+28h] BYREF
  int v12; // [rsp+70h] [rbp+30h] BYREF
  LPVOID pMem; // [rsp+78h] [rbp+38h] BYREF

  v12 = 0;
  v10 = L"defaultNamingContext";
  v11 = 0;
  v3 = (gCsOptions & 1) == 0;
  pMem = 0;
  *a2 = 0;
  if ( v3 )
    v5 = 101;
  else
    v5 = GetADsOpenObjectFlags() | 0x21;
  result = DSServerOpenDSObject(a1, L"LDAP://rootdse", v5, &v11);
  if ( (int)result >= 0 )
  {
    if ( (int)ADSIGetObjectAttributes(v11, &v10, 1, &pMem, &v12) >= 0 && v12 )
    {
      if ( *((_DWORD *)pMem + 6) )
        v7 = *(int **)(*((_QWORD *)pMem + 2) + 8LL);
      else
        v7 = 0;
    }
    else
    {
      v7 = &dword_1800314CC;
    }
    v8 = StringCchPrintfW(a2, 0x104u, L"%s%s", L"LDAP://", v7);
    ADSICloseDSObject(v11, v9);
    if ( pMem )
      FreeADsMem(pMem);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180023cdc  mov     [rsp-18h+arg_10], r8d
0x180023ce1  push    rbp
0x180023ce2  push    rbx
0x180023ce3  push    rdi
0x180023ce4  mov     rbp, rsp
0x180023ce7  sub     rsp, 40h
0x180023ceb  lea     rax, aDefaultnamingc; "defaultNamingContext"
0x180023cf2  mov     [rbp+arg_10], 0
0x180023cf9  mov     [rbp+var_10], rax
0x180023cfd  mov     rbx, rdx
0x180023d00  xor     eax, eax
0x180023d02  mov     [rbp+arg_8], 0
0x180023d0a  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x180023d11  mov     rdi, rcx
0x180023d14  mov     [rbp+pMem], 0
0x180023d1c  mov     [rdx], ax
0x180023d1f  jz      short loc_180023D2B
0x180023d21  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180023d26  or      eax, 21h
0x180023d29  jmp     short loc_180023D30
0x180023d2b  mov     eax, 65h ; 'e'
0x180023d30  lea     r9, [rbp+arg_8]; void **
0x180023d34  mov     r8d, eax; int
0x180023d37  lea     rdx, aLdapRootdse; "LDAP://rootdse"
0x180023d3e  mov     rcx, rdi; struct CServerContext *
0x180023d41  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180023d46  test    eax, eax
0x180023d48  js      loc_180023DD5
0x180023d4e  mov     rcx, [rbp+arg_8]
0x180023d52  lea     rax, [rbp+arg_10]
0x180023d56  lea     r9, [rbp+pMem]
0x180023d5a  mov     [rsp+40h+var_20], rax
0x180023d5f  mov     r8d, 1
0x180023d65  lea     rdx, [rbp+var_10]
0x180023d69  call    cs:__imp_ADSIGetObjectAttributes
0x180023d6f  test    eax, eax
0x180023d71  js      short loc_180023D91
0x180023d73  cmp     [rbp+arg_10], 0
0x180023d77  jz      short loc_180023D91
0x180023d79  mov     rax, [rbp+pMem]
0x180023d7d  cmp     dword ptr [rax+18h], 0
0x180023d81  jz      short loc_180023D8D
0x180023d83  mov     rax, [rax+10h]
0x180023d87  mov     rcx, [rax+8]
0x180023d8b  jmp     short loc_180023D98
0x180023d8d  xor     ecx, ecx
0x180023d8f  jmp     short loc_180023D98
0x180023d91  lea     rcx, dword_1800314CC
0x180023d98  mov     [rsp+40h+var_20], rcx
0x180023d9d  lea     r9, aLdap; "LDAP://"
0x180023da4  mov     rcx, rbx; unsigned __int16 *
0x180023da7  lea     r8, aSS_2; "%s%s"
0x180023dae  mov     edx, 104h; unsigned __int64
0x180023db3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023db8  mov     rcx, [rbp+arg_8]
0x180023dbc  mov     ebx, eax
0x180023dbe  call    cs:__imp_ADSICloseDSObject
0x180023dc4  mov     rcx, [rbp+pMem]; pMem
0x180023dc8  test    rcx, rcx
0x180023dcb  jz      short loc_180023DD3
0x180023dcd  call    cs:__imp_FreeADsMem
0x180023dd3  mov     eax, ebx
0x180023dd5  add     rsp, 40h
0x180023dd9  pop     rdi
0x180023dda  pop     rbx
0x180023ddb  pop     rbp
0x180023ddc  retn
```

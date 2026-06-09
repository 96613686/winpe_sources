# DeleteRepository(CServerContext *,ushort const *,ushort const *)

- ea: `0x180023bc0`
- end: `0x180023cd5`
- name: `?DeleteRepository@@YAJPEAVCServerContext@@PEBG1@Z`
- size: `277`
- prototype: `int __fastcall(struct CServerContext *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002371c`

## callees

- `0x18001d130`
- `0x18002350c`
- `0x180023bc0`

## import_xrefs

- `adsldpc!BuildADsPathFromParent` at `0x180023c34`
- `adsldpc!BuildADsPathFromParent` at `0x180023c34`
- `adsldpc!ADSICloseDSObject` at `0x180023c79`
- `adsldpc!ADSICloseDSObject` at `0x180023c88`
- `adsldpc!ADSICloseDSObject` at `0x180023ca3`
- `adsldpc!ADSICloseDSObject` at `0x180023cba`
- `adsldpc!ADSICloseDSObject` at `0x180023c79`
- `adsldpc!ADSICloseDSObject` at `0x180023c88`
- `adsldpc!ADSICloseDSObject` at `0x180023ca3`
- `adsldpc!ADSICloseDSObject` at `0x180023cba`
- `adsldpc!ADSIDeleteDSObject` at `0x180023c99`
- `adsldpc!ADSIDeleteDSObject` at `0x180023cb0`
- `adsldpc!ADSIDeleteDSObject` at `0x180023c99`
- `adsldpc!ADSIDeleteDSObject` at `0x180023cb0`
- `adsldpc!FreeADsMem` at `0x180023c66`
- `adsldpc!FreeADsMem` at `0x180023c66`

## pseudocode

```c
int __fastcall DeleteRepository(struct CServerContext *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // eax
  int result; // eax
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  void *v13; // [rsp+20h] [rbp-10h] BYREF
  LPVOID pMem; // [rsp+28h] [rbp-8h] BYREF
  void *v15; // [rsp+68h] [rbp+38h] BYREF

  v13 = 0;
  v15 = 0;
  pMem = 0;
  v6 = 101;
  if ( (gCsOptions & 1) != 0 )
    v7 = GetADsOpenObjectFlags() | 0x21;
  else
    v7 = 101;
  result = DSServerOpenDSObject(a1, a2, v7, &v13);
  if ( result >= 0 )
  {
    BuildADsPathFromParent(a2, a3, (unsigned __int16 **)&pMem);
    if ( (gCsOptions & 1) != 0 )
      v6 = GetADsOpenObjectFlags() | 0x21;
    v9 = DSServerOpenDSObject(a1, (const unsigned __int16 *)pMem, v6, &v15);
    FreeADsMem(pMem);
    if ( v9 >= 0 )
    {
      ADSIDeleteDSObject(v15, L"CN=Packages");
      ADSICloseDSObject(v15, v11);
      ADSIDeleteDSObject(v13, a3);
      ADSICloseDSObject(v13, v12);
      return 0;
    }
    else
    {
      if ( v15 )
        ADSICloseDSObject(v15, v10);
      if ( v13 )
        ADSICloseDSObject(v13, v10);
      return v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023bc0  mov     [rsp-18h+arg_0], rbx
0x180023bc5  mov     [rsp-18h+arg_8], rsi
0x180023bca  push    rbp
0x180023bcb  push    rdi
0x180023bcc  push    r14
0x180023bce  mov     rbp, rsp
0x180023bd1  sub     rsp, 30h
0x180023bd5  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x180023bdc  mov     rdi, r8
0x180023bdf  mov     rsi, rdx
0x180023be2  mov     [rbp+var_10], 0
0x180023bea  mov     r14, rcx
0x180023bed  mov     [rbp+arg_18], 0
0x180023bf5  mov     [rbp+pMem], 0
0x180023bfd  mov     ebx, 65h ; 'e'
0x180023c02  jz      short loc_180023C0E
0x180023c04  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180023c09  or      eax, 21h
0x180023c0c  jmp     short loc_180023C10
0x180023c0e  mov     eax, ebx
0x180023c10  lea     r9, [rbp+var_10]; void **
0x180023c14  mov     r8d, eax; int
0x180023c17  mov     rdx, rsi; unsigned __int16 *
0x180023c1a  mov     rcx, r14; struct CServerContext *
0x180023c1d  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180023c22  test    eax, eax
0x180023c24  js      loc_180023CC2
0x180023c2a  lea     r8, [rbp+pMem]
0x180023c2e  mov     rdx, rdi
0x180023c31  mov     rcx, rsi
0x180023c34  call    cs:__imp_?BuildADsPathFromParent@@YAJPEAG0PEAPEAG@Z; BuildADsPathFromParent(ushort *,ushort *,ushort * *)
0x180023c3a  test    byte ptr cs:?gCsOptions@@3KA, 1; ulong gCsOptions
0x180023c41  jz      short loc_180023C4D
0x180023c43  call    ?GetADsOpenObjectFlags@@YAKXZ; GetADsOpenObjectFlags(void)
0x180023c48  mov     ebx, eax
0x180023c4a  or      ebx, 21h
0x180023c4d  mov     rdx, [rbp+pMem]; unsigned __int16 *
0x180023c51  lea     r9, [rbp+arg_18]; void **
0x180023c55  mov     r8d, ebx; int
0x180023c58  mov     rcx, r14; struct CServerContext *
0x180023c5b  call    ?DSServerOpenDSObject@@YAJPEAVCServerContext@@PEBGJPEAPEAX@Z; DSServerOpenDSObject(CServerContext *,ushort const *,long,void * *)
0x180023c60  mov     rcx, [rbp+pMem]; pMem
0x180023c64  mov     ebx, eax
0x180023c66  call    cs:__imp_FreeADsMem
0x180023c6c  mov     rcx, [rbp+arg_18]
0x180023c70  test    ebx, ebx
0x180023c72  jns     short loc_180023C92
0x180023c74  test    rcx, rcx
0x180023c77  jz      short loc_180023C7F
0x180023c79  call    cs:__imp_ADSICloseDSObject
0x180023c7f  mov     rcx, [rbp+var_10]
0x180023c83  test    rcx, rcx
0x180023c86  jz      short loc_180023C8E
0x180023c88  call    cs:__imp_ADSICloseDSObject
0x180023c8e  mov     eax, ebx
0x180023c90  jmp     short loc_180023CC2
0x180023c92  lea     rdx, aCnPackages; "CN=Packages"
0x180023c99  call    cs:__imp_ADSIDeleteDSObject
0x180023c9f  mov     rcx, [rbp+arg_18]
0x180023ca3  call    cs:__imp_ADSICloseDSObject
0x180023ca9  mov     rcx, [rbp+var_10]
0x180023cad  mov     rdx, rdi
0x180023cb0  call    cs:__imp_ADSIDeleteDSObject
0x180023cb6  mov     rcx, [rbp+var_10]
0x180023cba  call    cs:__imp_ADSICloseDSObject
0x180023cc0  xor     eax, eax
0x180023cc2  mov     rbx, [rsp+30h+arg_0]
0x180023cc7  mov     rsi, [rsp+30h+arg_8]
0x180023ccc  add     rsp, 30h
0x180023cd0  pop     r14
0x180023cd2  pop     rdi
0x180023cd3  pop     rbp
0x180023cd4  retn
```

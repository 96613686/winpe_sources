# RdpCacheMan::CacheImportOffer(uint,_RDPGFX_CACHE_ENTRY_METADATA *)

- ea: `0x1800c6560`
- end: `0x1800c6860`
- name: `?CacheImportOffer@RdpCacheMan@@UEAAJIPEFAU_RDPGFX_CACHE_ENTRY_METADATA@@@Z`
- size: `768`
- prototype: `__int64 __fastcall(RdpCacheMan *this, unsigned int, struct _RDPGFX_CACHE_ENTRY_METADATA *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18002aafc`
- `0x18004f5bc`
- `0x180077aa0`
- `0x180079724`
- `0x180079770`
- `0x180079d2c`
- `0x18007a404`
- `0x18007f6fc`
- `0x1800c6560`
- `0x180158180`
- `0x18019b31c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c65f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c65f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6713`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c6713`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c65bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c65bf`

## string_xrefs

- `0x1800c683b`: `IID_IRdpCacheMan`
- `0x1800c659d`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800c65e5`: `ServerDisablePersistentCache`
- `0x1800c67cc`: `RDPGFX_CACHE_ENTRY_METADATA`
- `0x1800c682e`: `RdpCacheManError_CacheImportOfferFail`

## pseudocode

```c
__int64 __fastcall RdpCacheMan::CacheImportOffer(
        RdpCacheMan *this,
        unsigned int a2,
        struct _RDPGFX_CACHE_ENTRY_METADATA *a3)
{
  __int64 v4; // r15
  int v6; // ebx
  int v7; // esi
  unsigned int v8; // eax
  const wchar_t *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v14; // rax
  unsigned int v15; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  BYTE Data[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  char *Type; // [rsp+88h] [rbp+48h] BYREF

  v4 = a2;
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  LODWORD(Type) = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        110,
        &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
LABEL_24:
    v12 = -2147467259;
    Type = (char *)this + 24;
    CTSCriticalSection::Lock((RdpCacheMan *)((char *)this + 24));
    if ( !*((_DWORD *)this + 47) && (_DWORD)v4 )
    {
      v14 = operator new[](12 * v4);
      *((_QWORD *)this + 24) = v14;
      if ( !v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            111,
            (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
            v15,
            (__int64)"RDPGFX_CACHE_ENTRY_METADATA");
        }
        v12 = -2147024882;
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&Type);
        goto LABEL_34;
      }
      memcpy_0(v14, a3, 12 * v4);
      v12 = 0;
      *((_DWORD *)this + 47) = v4;
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&Type);
    if ( (v12 & 0x80000000) == 0 )
      return v12;
LABEL_34:
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpCacheMan",
      "RdpCacheManError_CacheImportOfferFail",
      (char *)0x95F,
      v12,
      phkResult);
    return v12;
  }
  v6 = 0;
  if ( RegQueryValueExW(hKey, L"ServerDisablePersistentCache", 0, (LPDWORD)&Type, Data, &cbData) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids, v11);
    }
  }
  else
  {
    v7 = (int)Type;
    if ( (_DWORD)Type == 4 )
    {
      LOBYTE(v6) = *(_DWORD *)Data != 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = L"false";
        if ( !v6 )
          v9 = L"true";
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          (unsigned int)&WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids,
          v8,
          (__int64)v9);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids, v10, v7);
    }
  }
  RegCloseKey(hKey);
  if ( !v6 )
    goto LABEL_24;
  return 0;
}

```

## disassembly

```asm
0x1800c6560  mov     [rsp-28h+arg_0], rbx
0x1800c6565  mov     [rsp-28h+arg_8], rsi
0x1800c656a  push    rbp
0x1800c656b  push    rdi
0x1800c656c  push    r12
0x1800c656e  push    r14
0x1800c6570  push    r15
0x1800c6572  mov     rbp, rsp
0x1800c6575  sub     rsp, 40h
0x1800c6579  mov     r12, r8
0x1800c657c  mov     r15d, edx
0x1800c657f  mov     r14, rcx
0x1800c6582  mov     [rbp+hKey], 0
0x1800c658a  lea     rax, [rbp+hKey]
0x1800c658e  mov     dword ptr [rbp+Data], 0
0x1800c6595  xor     r8d, r8d; ulOptions
0x1800c6598  mov     [rsp+40h+phkResult], rax; int
0x1800c659d  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x1800c65a4  mov     [rbp+cbData], 4
0x1800c65ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c65b2  mov     dword ptr [rbp+Type], 0
0x1800c65b9  mov     r9d, 20019h; samDesired
0x1800c65bf  call    cs:__imp_RegOpenKeyExW
0x1800c65c5  test    eax, eax
0x1800c65c7  jnz     loc_1800C6724
0x1800c65cd  mov     rcx, [rbp+hKey]; hKey
0x1800c65d1  lea     rax, [rbp+cbData]
0x1800c65d5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800c65da  lea     r9, [rbp+Type]; lpType
0x1800c65de  lea     rax, [rbp+Data]
0x1800c65e2  xor     r8d, r8d; lpReserved
0x1800c65e5  lea     rdx, aServerdisablep; "ServerDisablePersistentCache"
0x1800c65ec  mov     [rsp+40h+phkResult], rax; lpData
0x1800c65f1  xor     ebx, ebx
0x1800c65f3  call    cs:__imp_RegQueryValueExW
0x1800c65f9  test    eax, eax
0x1800c65fb  jnz     loc_1800C66C9
0x1800c6601  mov     esi, dword ptr [rbp+Type]
0x1800c6604  cmp     esi, 4
0x1800c6607  jnz     short loc_1800C667D
0x1800c6609  cmp     dword ptr [rbp+Data], ebx
0x1800c660c  setnz   bl
0x1800c660f  mov     rax, cs:WPP_GLOBAL_Control
0x1800c6616  lea     rdi, WPP_GLOBAL_Control
0x1800c661d  cmp     rax, rdi
0x1800c6620  jz      loc_1800C670F
0x1800c6626  test    dword ptr [rax+1Ch], 100h
0x1800c662d  jz      loc_1800C670F
0x1800c6633  cmp     [rax+19h], sil
0x1800c6637  jb      loc_1800C670F
0x1800c663d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c6642  lea     rdx, aTrue; "true"
0x1800c6649  test    ebx, ebx
0x1800c664b  lea     rcx, aFalse; "false"
0x1800c6652  mov     r9d, eax
0x1800c6655  cmovz   rcx, rdx
0x1800c6659  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x1800c6660  mov     [rsp+40h+phkResult], rcx
0x1800c6665  lea     edx, [rsi+67h]
0x1800c6668  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c666f  mov     rcx, [rcx+10h]
0x1800c6673  call    WPP_SF_DS
0x1800c6678  jmp     loc_1800C670F
0x1800c667d  mov     rax, cs:WPP_GLOBAL_Control
0x1800c6684  lea     rdi, WPP_GLOBAL_Control
0x1800c668b  cmp     rax, rdi
0x1800c668e  jz      short loc_1800C670F
0x1800c6690  test    dword ptr [rax+1Ch], 100h
0x1800c6697  jz      short loc_1800C670F
0x1800c6699  cmp     byte ptr [rax+19h], 3
0x1800c669d  jb      short loc_1800C670F
0x1800c669f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c66a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c66ab  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x1800c66b2  mov     edx, 6Dh ; 'm'
0x1800c66b7  mov     dword ptr [rsp+40h+phkResult], esi
0x1800c66bb  mov     r9d, eax
0x1800c66be  mov     rcx, [rcx+10h]
0x1800c66c2  call    WPP_SF_Dd
0x1800c66c7  jmp     short loc_1800C670F
0x1800c66c9  mov     rax, cs:WPP_GLOBAL_Control
0x1800c66d0  lea     rdi, WPP_GLOBAL_Control
0x1800c66d7  cmp     rax, rdi
0x1800c66da  jz      short loc_1800C670F
0x1800c66dc  test    dword ptr [rax+1Ch], 100h
0x1800c66e3  jz      short loc_1800C670F
0x1800c66e5  cmp     byte ptr [rax+19h], 3
0x1800c66e9  jb      short loc_1800C670F
0x1800c66eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c66f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c66f7  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x1800c66fe  mov     edx, 6Ch ; 'l'
0x1800c6703  mov     r9d, eax
0x1800c6706  mov     rcx, [rcx+10h]
0x1800c670a  call    WPP_SF_d
0x1800c670f  mov     rcx, [rbp+hKey]; hKey
0x1800c6713  call    cs:__imp_RegCloseKey
0x1800c6719  test    ebx, ebx
0x1800c671b  jz      short loc_1800C676A
0x1800c671d  xor     ebx, ebx
0x1800c671f  jmp     loc_1800C6847
0x1800c6724  mov     rax, cs:WPP_GLOBAL_Control
0x1800c672b  lea     rdi, WPP_GLOBAL_Control
0x1800c6732  cmp     rax, rdi
0x1800c6735  jz      short loc_1800C676A
0x1800c6737  test    dword ptr [rax+1Ch], 100h
0x1800c673e  jz      short loc_1800C676A
0x1800c6740  cmp     byte ptr [rax+19h], 3
0x1800c6744  jb      short loc_1800C676A
0x1800c6746  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c674b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6752  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x1800c6759  mov     edx, 6Eh ; 'n'
0x1800c675e  mov     r9d, eax
0x1800c6761  mov     rcx, [rcx+10h]
0x1800c6765  call    WPP_SF_d
0x1800c676a  lea     rcx, [r14+18h]; this
0x1800c676e  mov     ebx, 80004005h
0x1800c6773  mov     [rbp+Type], rcx
0x1800c6777  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800c677c  cmp     dword ptr [r14+0BCh], 0
0x1800c6784  jnz     loc_1800C681E
0x1800c678a  test    r15d, r15d
0x1800c678d  jz      loc_1800C681E
0x1800c6793  lea     rbx, [r15+r15*2]
0x1800c6797  shl     rbx, 2
0x1800c679b  mov     rcx, rbx; unsigned __int64
0x1800c679e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c67a3  mov     [r14+0C0h], rax
0x1800c67aa  test    rax, rax
0x1800c67ad  jnz     short loc_1800C6807
0x1800c67af  mov     rax, cs:WPP_GLOBAL_Control
0x1800c67b6  cmp     rax, rdi
0x1800c67b9  jz      short loc_1800C67F7
0x1800c67bb  test    byte ptr [rax+1Ch], 8
0x1800c67bf  jz      short loc_1800C67F7
0x1800c67c1  cmp     byte ptr [rax+19h], 2
0x1800c67c5  jb      short loc_1800C67F7
0x1800c67c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c67cc  lea     rcx, aRdpgfxCacheEnt; "RDPGFX_CACHE_ENTRY_METADATA"
0x1800c67d3  mov     edx, 6Fh ; 'o'
0x1800c67d8  mov     [rsp+40h+phkResult], rcx
0x1800c67dd  lea     r8, WPP_2283bfa6a8443edd568982bc06f187aa_Traceguids
0x1800c67e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c67eb  mov     r9d, eax
0x1800c67ee  mov     rcx, [rcx+10h]
0x1800c67f2  call    WPP_SF_Ds
0x1800c67f7  lea     rcx, [rbp+Type]; this
0x1800c67fb  mov     ebx, 8007000Eh
0x1800c6800  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800c6805  jmp     short loc_1800C682B
0x1800c6807  mov     r8, rbx; Size
0x1800c680a  mov     rdx, r12; Src
0x1800c680d  mov     rcx, rax; void *
0x1800c6810  call    memcpy_0
0x1800c6815  xor     ebx, ebx
0x1800c6817  mov     [r14+0BCh], r15d
0x1800c681e  lea     rcx, [rbp+Type]; this
0x1800c6822  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800c6827  test    ebx, ebx
0x1800c6829  jns     short loc_1800C6847
0x1800c682b  mov     r9d, ebx; unsigned int
0x1800c682e  lea     rdx, aRdpcachemanerr_4; "RdpCacheManError_CacheImportOfferFail"
0x1800c6835  mov     r8d, 95Fh; char *
0x1800c683b  lea     rcx, aIidIrdpcachema; "IID_IRdpCacheMan"
0x1800c6842  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800c6847  mov     rsi, [rsp+40h+arg_8]
0x1800c684c  mov     eax, ebx
0x1800c684e  mov     rbx, [rsp+40h+arg_0]
0x1800c6853  add     rsp, 40h
0x1800c6857  pop     r15
0x1800c6859  pop     r14
0x1800c685b  pop     r12
0x1800c685d  pop     rdi
0x1800c685e  pop     rbp
0x1800c685f  retn
```

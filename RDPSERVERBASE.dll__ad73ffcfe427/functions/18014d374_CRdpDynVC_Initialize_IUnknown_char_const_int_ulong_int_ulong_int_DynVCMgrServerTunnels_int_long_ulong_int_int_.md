# CRdpDynVC::Initialize(IUnknown *,char const *,int,ulong,int,ulong,int,DynVCMgrServerTunnels,int,long,ulong,int,int,ulong,CRdpDynVCMgr *)

- ea: `0x18014d374`
- end: `0x18014d852`
- name: `?Initialize@CRdpDynVC@@QEAAJPEAUIUnknown@@PEBDHKHKHW4DynVCMgrServerTunnels@@HJKHHKPEAVCRdpDynVCMgr@@@Z`
- size: `1246`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x180069f98`
- `0x180142140`

## callees

- `0x18000cdac`
- `0x18000cddc`
- `0x18000f660`
- `0x18004c8a8`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007f330`
- `0x18007f6fc`
- `0x18007f76c`
- `0x18014be54`
- `0x18014cfa0`
- `0x18014d0dc`
- `0x18014d374`
- `0x18014ddf8`
- `0x18015008c`
- `0x18019b31c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d65d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d4dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014d65d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014d64b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014d64b`

## string_xrefs

- `0x18014d6ab`: `Failed CreateEvent call for m_hChannelCloseEvent`

## pseudocode

```c
__int64 __fastcall CRdpDynVC::Initialize(
        __int64 a1,
        struct IUnknown *a2,
        _BYTE *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        int a15,
        __int64 a16)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v21; // edx
  int v22; // r8d
  signed int v23; // ebx
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // rcx
  __int64 v27; // rsi
  signed int LastError; // eax
  unsigned int v29; // esi
  void *v30; // rax
  unsigned int v31; // eax
  __int64 v32; // rsi
  HANDLE EventW; // rax
  signed int v34; // eax
  _DWORD *v35; // rcx
  CDynVCStat *v36; // rax
  CDynVCStat *v37; // rbx
  __int64 v38; // rcx
  unsigned int v39; // eax
  __int64 v41; // [rsp+28h] [rbp-A0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsddddDdDDddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      v22,
      CurrentThreadActivityIdPrefix,
      (__int64)a3,
      a4,
      a6,
      a7,
      a8,
      a9,
      a10,
      a11,
      a12,
      a15,
      a13,
      a14);
  }
  v23 = CRdpDynVC::Initialize((CRdpDynVC *)a1, a2);
  if ( v23 >= 0 )
  {
    v27 = -1;
    do
      ++v27;
    while ( a3[v27] );
    if ( (unsigned int)CTSCriticalSection::Initialize((CTSCriticalSection *)(a1 + 72)) )
      goto LABEL_21;
    LastError = GetLastError();
    v23 = LastError;
    if ( LastError > 0 )
      v23 = (unsigned __int16)LastError | 0x80070000;
    if ( v23 >= 0 )
    {
LABEL_21:
      v29 = v27 + 1;
      v30 = operator new[](v29);
      *(_QWORD *)(a1 + 112) = v30;
      if ( v30 )
      {
        memcpy_0(v30, a3, v29);
        *(_BYTE *)(v29 - 1 + *(_QWORD *)(a1 + 112)) = 0;
        if ( !a16 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v31 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ds(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              (unsigned int)&WPP_5f512622d6a231ba5b291ba800e4e815_Traceguids,
              v31,
              (__int64)"pMgr");
          }
          return (unsigned int)-2147467261;
        }
        v32 = a1 + 128;
        if ( a16 != *(_QWORD *)(a1 + 128) )
        {
          TCntPtr<CFakeGfxProvider>::SafeRelease(a1 + 128);
          *(_QWORD *)v32 = a16;
          TCntPtr<PipePrimitive>::SafeAddRef(a1 + 128);
        }
        *(_DWORD *)(a1 + 156) = a6;
        *(_DWORD *)(a1 + 160) = a5;
        *(_DWORD *)(a1 + 168) = a7;
        *(_DWORD *)(a1 + 164) = a8;
        *(_DWORD *)(a1 + 120) = a4;
        *(_DWORD *)(a1 + 172) = a9;
        *(_DWORD *)(a1 + 176) = a12;
        *(_DWORD *)(a1 + 152) = a15;
        EventW = CreateEventW(0, 1, 0, 0);
        *(_QWORD *)(a1 + 304) = EventW;
        if ( !EventW )
        {
          v34 = GetLastError();
          v23 = v34;
          if ( v34 > 0 )
            v23 = (unsigned __int16)v34 | 0x80070000;
          if ( v23 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v24 = RdpWppGetCurrentThreadActivityIdPrefix();
              v25 = 22;
              v26 = "Failed CreateEvent call for m_hChannelCloseEvent";
              goto LABEL_10;
            }
            return (unsigned int)v23;
          }
        }
        if ( (*(_BYTE *)(a1 + 160) & 0xF8) == 0 )
          o__strlwr_0(*(char **)(a1 + 112));
        *(_DWORD *)(a1 + 28) |= 2u;
        v35 = *(_DWORD **)v32;
        if ( *(_DWORD *)(*(_QWORD *)v32 + 268LL) )
        {
          *(_DWORD *)(a1 + 336) = v35[71];
          *(_DWORD *)(a1 + 328) = 4;
        }
        if ( v35[87] )
        {
          *(_DWORD *)(a1 + 332) = v35[91];
          *(_DWORD *)(a1 + 324) = 4;
        }
        if ( a10 )
          CRdpDynVC::OnTunnelBoundHandler((CRdpDynVC *)a1, a11);
        if ( a13 )
          CRdpDynVC::OnAllSvcJoinedHandler((CRdpDynVC *)a1, a14);
        v36 = (CDynVCStat *)operator new(0x418u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v36 )
          v37 = CDynVCStat::CDynVCStat(v36);
        else
          v37 = 0;
        if ( v37 != *(CDynVCStat **)(a1 + 344) )
        {
          TCntPtr<CFakeGfxProvider>::SafeRelease(a1 + 344);
          *(_QWORD *)(a1 + 344) = v37;
          TCntPtr<PipePrimitive>::SafeAddRef(a1 + 344);
        }
        v38 = *(_QWORD *)(a1 + 344);
        if ( v38 )
        {
          v23 = CDynVCStat::Initialize((CDynVCStat *)(v38 + 8));
          if ( v23 >= 0 )
            return 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v24 = RdpWppGetCurrentThreadActivityIdPrefix();
            v25 = 25;
            v26 = "CDynVCStat::Initialize failed";
            goto LABEL_10;
          }
          return (unsigned int)v23;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)&WPP_5f512622d6a231ba5b291ba800e4e815_Traceguids,
            v39,
            (__int64)"CDynVCStat");
        }
      }
      return (unsigned int)-2147024882;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 20;
      v26 = "m_objLock.Initialize";
      goto LABEL_10;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 19;
    v26 = "Platform initialize failed";
LABEL_10:
    LODWORD(v41) = v23;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      (unsigned int)&WPP_5f512622d6a231ba5b291ba800e4e815_Traceguids,
      v24,
      (__int64)v26,
      v41);
  }
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18014d374  push    rbx
0x18014d376  push    rbp
0x18014d377  push    rsi
0x18014d378  push    rdi
0x18014d379  push    r12
0x18014d37b  push    r13
0x18014d37d  push    r14
0x18014d37f  push    r15
0x18014d381  sub     rsp, 88h
0x18014d388  mov     r14d, r9d
0x18014d38b  mov     rbp, r8
0x18014d38e  mov     rbx, rdx
0x18014d391  mov     rdi, rcx
0x18014d394  mov     rax, cs:WPP_GLOBAL_Control
0x18014d39b  lea     rsi, WPP_GLOBAL_Control
0x18014d3a2  mov     r15d, [rsp+0C8h+arg_70]
0x18014d3aa  mov     r12d, [rsp+0C8h+arg_58]
0x18014d3b2  mov     r13d, [rsp+0C8h+arg_40]
0x18014d3ba  cmp     rax, rsi
0x18014d3bd  jz      loc_18014D454
0x18014d3c3  test    dword ptr [rax+1Ch], 800h
0x18014d3ca  jz      loc_18014D454
0x18014d3d0  cmp     byte ptr [rax+19h], 4
0x18014d3d4  jb      short loc_18014D454
0x18014d3d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014d3db  mov     ecx, [rsp+0C8h+arg_68]
0x18014d3e2  mov     r9d, eax
0x18014d3e5  mov     [rsp+0C8h+var_50], ecx
0x18014d3e9  mov     ecx, [rsp+0C8h+arg_60]
0x18014d3f0  mov     [rsp+0C8h+var_58], ecx
0x18014d3f4  mov     ecx, [rsp+0C8h+arg_50]
0x18014d3fb  mov     [rsp+0C8h+var_60], r15d
0x18014d400  mov     [rsp+0C8h+var_68], r12d
0x18014d405  mov     [rsp+0C8h+var_70], ecx
0x18014d409  mov     ecx, [rsp+0C8h+arg_48]
0x18014d410  mov     [rsp+0C8h+var_78], ecx
0x18014d414  mov     ecx, [rsp+0C8h+arg_38]
0x18014d41b  mov     [rsp+0C8h+var_80], r13d
0x18014d420  mov     [rsp+0C8h+var_88], ecx
0x18014d424  mov     ecx, [rsp+0C8h+arg_30]
0x18014d42b  mov     [rsp+0C8h+var_90], ecx
0x18014d42f  mov     ecx, [rsp+0C8h+arg_28]
0x18014d436  mov     [rsp+0C8h+var_98], ecx
0x18014d43a  mov     rcx, cs:WPP_GLOBAL_Control
0x18014d441  mov     dword ptr [rsp+0C8h+var_A0], r14d
0x18014d446  mov     [rsp+0C8h+var_A8], rbp
0x18014d44b  mov     rcx, [rcx+10h]
0x18014d44f  call    WPP_SF_DsddddDdDDddd
0x18014d454  mov     rdx, rbx; struct IUnknown *
0x18014d457  mov     rcx, rdi; this
0x18014d45a  call    ?Initialize@CRdpDynVC@@QEAAJPEAUIUnknown@@@Z; CRdpDynVC::Initialize(IUnknown *)
0x18014d45f  mov     ebx, eax
0x18014d461  test    eax, eax
0x18014d463  jns     short loc_18014D4C2
0x18014d465  mov     rax, cs:WPP_GLOBAL_Control
0x18014d46c  cmp     rax, rsi
0x18014d46f  jz      loc_18014D83C
0x18014d475  test    byte ptr [rax+1Ch], 8
0x18014d479  jz      loc_18014D83C
0x18014d47f  cmp     byte ptr [rax+19h], 2
0x18014d483  jb      loc_18014D83C
0x18014d489  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014d48e  mov     edx, 13h
0x18014d493  lea     rcx, aPlatformInitia; "Platform initialize failed"
0x18014d49a  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x18014d49e  lea     r8, WPP_5f512622d6a231ba5b291ba800e4e815_Traceguids
0x18014d4a5  mov     [rsp+0C8h+var_A8], rcx
0x18014d4aa  mov     r9d, eax
0x18014d4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18014d4b4  mov     rcx, [rcx+10h]
0x18014d4b8  call    WPP_SF_DsD
0x18014d4bd  jmp     loc_18014D83C
0x18014d4c2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18014d4c6  inc     rsi
0x18014d4c9  cmp     byte ptr [rsi+rbp], 0
0x18014d4cd  jnz     short loc_18014D4C6
0x18014d4cf  lea     rcx, [rdi+48h]; this
0x18014d4d3  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18014d4d8  test    eax, eax
0x18014d4da  jnz     short loc_18014D536
0x18014d4dc  call    cs:__imp_GetLastError
0x18014d4e2  mov     ebx, eax
0x18014d4e4  test    eax, eax
0x18014d4e6  jle     short loc_18014D4F1
0x18014d4e8  movzx   ebx, ax
0x18014d4eb  or      ebx, 80070000h
0x18014d4f1  test    ebx, ebx
0x18014d4f3  jns     short loc_18014D536
0x18014d4f5  mov     rax, cs:WPP_GLOBAL_Control
0x18014d4fc  lea     rcx, WPP_GLOBAL_Control
0x18014d503  cmp     rax, rcx
0x18014d506  jz      loc_18014D83C
0x18014d50c  test    byte ptr [rax+1Ch], 8
0x18014d510  jz      loc_18014D83C
0x18014d516  cmp     byte ptr [rax+19h], 2
0x18014d51a  jb      loc_18014D83C
0x18014d520  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014d525  mov     edx, 14h
0x18014d52a  lea     rcx, aMObjlockInitia; "m_objLock.Initialize"
0x18014d531  jmp     loc_18014D49A
0x18014d536  inc     esi
0x18014d538  mov     ecx, esi; unsigned __int64
0x18014d53a  mov     ebx, esi
0x18014d53c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18014d541  mov     [rdi+70h], rax
0x18014d545  test    rax, rax
0x18014d548  jnz     short loc_18014D554
0x18014d54a  mov     ebx, 8007000Eh
0x18014d54f  jmp     loc_18014D83C
0x18014d554  mov     r8, rbx; Size
0x18014d557  mov     rdx, rbp; Src
0x18014d55a  mov     rcx, rax; void *
0x18014d55d  call    memcpy_0
0x18014d562  mov     rax, [rdi+70h]
0x18014d566  lea     ecx, [rsi-1]
0x18014d569  mov     rbx, [rsp+0C8h+arg_78]
0x18014d571  xor     ebp, ebp
0x18014d573  mov     [rcx+rax], bpl
0x18014d577  test    rbx, rbx
0x18014d57a  jnz     short loc_18014D5D3
0x18014d57c  mov     rax, cs:WPP_GLOBAL_Control
0x18014d583  lea     rcx, WPP_GLOBAL_Control
0x18014d58a  cmp     rax, rcx
0x18014d58d  jz      short loc_18014D5C9
0x18014d58f  test    byte ptr [rax+1Ch], 8
0x18014d593  jz      short loc_18014D5C9
0x18014d595  cmp     byte ptr [rax+19h], 2
0x18014d599  jb      short loc_18014D5C9
0x18014d59b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014d5a0  lea     rcx, aPmgr; "pMgr"
0x18014d5a7  mov     r9d, eax
0x18014d5aa  mov     [rsp+0C8h+var_A8], rcx
0x18014d5af  lea     edx, [rbp+15h]
0x18014d5b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18014d5b9  lea     r8, WPP_5f512622d6a231ba5b291ba800e4e815_Traceguids
0x18014d5c0  mov     rcx, [rcx+10h]
0x18014d5c4  call    WPP_SF_Ds
0x18014d5c9  mov     ebx, 80004003h
0x18014d5ce  jmp     loc_18014D83C
0x18014d5d3  lea     rsi, [rdi+80h]
0x18014d5da  cmp     rbx, [rsi]
0x18014d5dd  jz      short loc_18014D5F2
0x18014d5df  mov     rcx, rsi
0x18014d5e2  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18014d5e7  mov     rcx, rsi
0x18014d5ea  mov     [rsi], rbx
0x18014d5ed  call    ?SafeAddRef@?$TCntPtr@VPipePrimitive@@@@AEAAXXZ; TCntPtr<PipePrimitive>::SafeAddRef(void)
0x18014d5f2  mov     eax, [rsp+0C8h+arg_28]
0x18014d5f9  xor     r9d, r9d; lpName
0x18014d5fc  mov     [rdi+9Ch], eax
0x18014d602  xor     r8d, r8d; bInitialState
0x18014d605  mov     eax, [rsp+0C8h+arg_20]
0x18014d60c  xor     ecx, ecx; lpEventAttributes
0x18014d60e  mov     [rdi+0A0h], eax
0x18014d614  mov     eax, [rsp+0C8h+arg_30]
0x18014d61b  lea     edx, [r9+1]; bManualReset
0x18014d61f  mov     [rdi+0A8h], eax
0x18014d625  mov     eax, [rsp+0C8h+arg_38]
0x18014d62c  mov     [rdi+0A4h], eax
0x18014d632  mov     [rdi+78h], r14d
0x18014d636  mov     [rdi+0ACh], r13d
0x18014d63d  mov     [rdi+0B0h], r12d
0x18014d644  mov     [rdi+98h], r15d
0x18014d64b  call    cs:__imp_CreateEventW
0x18014d651  mov     [rdi+130h], rax
0x18014d658  test    rax, rax
0x18014d65b  jnz     short loc_18014D6B7
0x18014d65d  call    cs:__imp_GetLastError
0x18014d663  mov     ebx, eax
0x18014d665  test    eax, eax
0x18014d667  jle     short loc_18014D672
0x18014d669  movzx   ebx, ax
0x18014d66c  or      ebx, 80070000h
0x18014d672  test    ebx, ebx
0x18014d674  jns     short loc_18014D6B7
0x18014d676  mov     rax, cs:WPP_GLOBAL_Control
0x18014d67d  lea     rcx, WPP_GLOBAL_Control
0x18014d684  cmp     rax, rcx
0x18014d687  jz      loc_18014D83C
0x18014d68d  test    byte ptr [rax+1Ch], 8
0x18014d691  jz      loc_18014D83C
0x18014d697  cmp     byte ptr [rax+19h], 2
0x18014d69b  jb      loc_18014D83C
0x18014d6a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014d6a6  mov     edx, 16h
0x18014d6ab  lea     rcx, aFailedCreateev_0; "Failed CreateEvent call for m_hChannelC"...
0x18014d6b2  jmp     loc_18014D49A
0x18014d6b7  test    byte ptr [rdi+0A0h], 0F8h
0x18014d6be  jnz     short loc_18014D6C9
0x18014d6c0  mov     rcx, [rdi+70h]; String
0x18014d6c4  call    _o__strlwr_0
0x18014d6c9  or      dword ptr [rdi+1Ch], 2
0x18014d6cd  mov     rcx, [rsi]
0x18014d6d0  cmp     [rcx+10Ch], ebp
0x18014d6d6  jz      short loc_18014D6EE
0x18014d6d8  mov     eax, [rcx+11Ch]
0x18014d6de  mov     [rdi+150h], eax
0x18014d6e4  mov     dword ptr [rdi+148h], 4
0x18014d6ee  cmp     [rcx+15Ch], ebp
0x18014d6f4  jz      short loc_18014D70C
0x18014d6f6  mov     eax, [rcx+16Ch]
0x18014d6fc  mov     [rdi+14Ch], eax
0x18014d702  mov     dword ptr [rdi+144h], 4
0x18014d70c  cmp     [rsp+0C8h+arg_48], ebp
0x18014d713  jz      short loc_18014D724
0x18014d715  mov     edx, [rsp+0C8h+arg_50]; int
0x18014d71c  mov     rcx, rdi; this
0x18014d71f  call    ?OnTunnelBoundHandler@CRdpDynVC@@IEAAXJ@Z; CRdpDynVC::OnTunnelBoundHandler(long)
0x18014d724  cmp     [rsp+0C8h+arg_60], ebp
0x18014d72b  jz      short loc_18014D73C
0x18014d72d  mov     edx, [rsp+0C8h+arg_68]; int
0x18014d734  mov     rcx, rdi; this
0x18014d737  call    ?OnAllSvcJoinedHandler@CRdpDynVC@@IEAAXH@Z; CRdpDynVC::OnAllSvcJoinedHandler(int)
0x18014d73c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18014d743  mov     ecx, 418h; unsigned __int64
0x18014d748  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18014d74d  test    rax, rax
0x18014d750  jz      short loc_18014D75F
0x18014d752  mov     rcx, rax; this
0x18014d755  call    ??0CDynVCStat@@QEAA@XZ; CDynVCStat::CDynVCStat(void)
0x18014d75a  mov     rbx, rax
0x18014d75d  jmp     short loc_18014D762
0x18014d75f  mov     rbx, rbp
0x18014d762  cmp     rbx, [rdi+158h]
0x18014d769  jz      short loc_18014D78A
0x18014d76b  lea     rcx, [rdi+158h]
0x18014d772  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x18014d777  lea     rcx, [rdi+158h]
0x18014d77e  mov     [rdi+158h], rbx
0x18014d785  call    ?SafeAddRef@?$TCntPtr@VPipePrimitive@@@@AEAAXXZ; TCntPtr<PipePrimitive>::SafeAddRef(void)
0x18014d78a  mov     rcx, [rdi+158h]
0x18014d791  test    rcx, rcx
0x18014d794  jnz     short loc_18014D7F6
0x18014d796  mov     rax, cs:WPP_GLOBAL_Control
0x18014d79d  lea     rcx, WPP_GLOBAL_Control
0x18014d7a4  cmp     rax, rcx
0x18014d7a7  jz      loc_18014D54A
0x18014d7ad  test    byte ptr [rax+1Ch], 8
0x18014d7b1  jz      loc_18014D54A
0x18014d7b7  cmp     byte ptr [rax+19h], 2
0x18014d7bb  jb      loc_18014D54A
0x18014d7c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014d7c6  lea     rcx, aCdynvcstat; "CDynVCStat"
0x18014d7cd  mov     edx, 18h
0x18014d7d2  mov     [rsp+0C8h+var_A8], rcx
0x18014d7d7  lea     r8, WPP_5f512622d6a231ba5b291ba800e4e815_Traceguids
0x18014d7de  mov     rcx, cs:WPP_GLOBAL_Control
0x18014d7e5  mov     r9d, eax
0x18014d7e8  mov     rcx, [rcx+10h]
0x18014d7ec  call    WPP_SF_Ds
0x18014d7f1  jmp     loc_18014D54A
0x18014d7f6  add     rcx, 8; this
0x18014d7fa  call    ?Initialize@CDynVCStat@@UEAAJXZ; CDynVCStat::Initialize(void)
0x18014d7ff  mov     ebx, eax
0x18014d801  test    eax, eax
0x18014d803  jns     short loc_18014D83A
0x18014d805  mov     rax, cs:WPP_GLOBAL_Control
0x18014d80c  lea     rcx, WPP_GLOBAL_Control
0x18014d813  cmp     rax, rcx
0x18014d816  jz      short loc_18014D83C
0x18014d818  test    byte ptr [rax+1Ch], 8
0x18014d81c  jz      short loc_18014D83C
0x18014d81e  cmp     byte ptr [rax+19h], 2
0x18014d822  jb      short loc_18014D83C
0x18014d824  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18014d829  mov     edx, 19h
0x18014d82e  lea     rcx, aCdynvcstatInit; "CDynVCStat::Initialize failed"
0x18014d835  jmp     loc_18014D49A
0x18014d83a  mov     ebx, ebp
0x18014d83c  mov     eax, ebx
0x18014d83e  add     rsp, 88h
0x18014d845  pop     r15
0x18014d847  pop     r14
0x18014d849  pop     r13
0x18014d84b  pop     r12
0x18014d84d  pop     rdi
0x18014d84e  pop     rsi
0x18014d84f  pop     rbp
0x18014d850  pop     rbx
0x18014d851  retn
```

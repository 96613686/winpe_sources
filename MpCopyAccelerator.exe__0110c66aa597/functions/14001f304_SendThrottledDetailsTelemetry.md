# SendThrottledDetailsTelemetry

- ea: `0x14001f304`
- end: `0x14001f6a0`
- name: `SendThrottledDetailsTelemetry`
- size: `924`
- prototype: `__int64 __usercall@<rax>(unsigned int *@<rcx>, CommonUtil *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001f6a0`

## callees

- `0x1400010ac`
- `0x140004054`
- `0x14000405c`
- `0x140004294`
- `0x140005c20`
- `0x14000bb44`
- `0x14001da70`
- `0x14001e654`
- `0x14001eee0`
- `0x14001f304`
- `0x140024148`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x14001f3cb`
- `MpClient!MpFreeMemory` at `0x14001f675`
- `MpClient!MpFreeMemory` at `0x14001f3cb`
- `MpClient!MpFreeMemory` at `0x14001f675`

## pseudocode

```c
__int64 __fastcall SendThrottledDetailsTelemetry(
        unsigned int *a1,
        unsigned int a2,
        char a3,
        CommonUtil *a4,
        CommonUtil *a5,
        int a6,
        int a7)
{
  int v11; // eax
  int ClientProcessName; // eax
  unsigned __int64 *v14; // r9
  int FilenameFromPathW; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned __int64 *v18; // r9
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  wchar_t *v20; // rbx
  __int64 v21; // [rsp+D0h] [rbp-80h] BYREF
  wchar_t *v22; // [rsp+D8h] [rbp-78h] BYREF
  int v23; // [rsp+E0h] [rbp-70h] BYREF
  int v24; // [rsp+E4h] [rbp-6Ch] BYREF
  int v25; // [rsp+E8h] [rbp-68h] BYREF
  int v26; // [rsp+ECh] [rbp-64h] BYREF
  int v27; // [rsp+F0h] [rbp-60h] BYREF
  int v28; // [rsp+F4h] [rbp-5Ch] BYREF
  int v29; // [rsp+F8h] [rbp-58h] BYREF
  int v30; // [rsp+FCh] [rbp-54h] BYREF
  int v31; // [rsp+100h] [rbp-50h] BYREF
  __int64 v32[2]; // [rsp+108h] [rbp-48h] BYREF
  __int64 v33; // [rsp+118h] [rbp-38h] BYREF
  __int64 v34; // [rsp+120h] [rbp-30h] BYREF
  __int64 v35; // [rsp+128h] [rbp-28h] BYREF
  __int64 v36; // [rsp+130h] [rbp-20h] BYREF
  __int64 v37; // [rsp+138h] [rbp-18h] BYREF
  __int64 v38; // [rsp+140h] [rbp-10h] BYREF
  __int64 v39; // [rsp+148h] [rbp-8h] BYREF
  __int64 v40; // [rsp+150h] [rbp+0h] BYREF
  __int64 v41; // [rsp+158h] [rbp+8h] BYREF
  __int64 v42; // [rsp+160h] [rbp+10h] BYREF
  wchar_t v43[4]; // [rsp+168h] [rbp+18h] BYREF
  wchar_t v44[4]; // [rsp+170h] [rbp+20h] BYREF
  wchar_t *v45; // [rsp+178h] [rbp+28h] BYREF

  v11 = rand();
  if ( v11 != 100 * (v11 / 100) )
    return 2147500037LL;
  v22 = 0;
  ClientProcessName = GetClientProcessName(a1, &v22);
  FilenameFromPathW = ClientProcessName;
  if ( ClientProcessName < 0 )
  {
    MpCmdLogPrintf(L"Failed to get client process name, hr=%#lx\n", (unsigned int)ClientProcessName);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 32;
LABEL_7:
      WPP_SF_d(v16[2], v17, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, (unsigned int)FilenameFromPathW);
      goto LABEL_8;
    }
    goto LABEL_8;
  }
  *(_QWORD *)v44 = 0;
  v45 = 0;
  FilenameFromPathW = CommonUtil::UtilGetFilenameFromPathW(a4, v44, (const wchar_t **)&v45, v14);
  if ( FilenameFromPathW < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 33;
      goto LABEL_7;
    }
LABEL_8:
    if ( v22 )
      MpFreeMemory(v22);
    return (unsigned int)FilenameFromPathW;
  }
  *(_QWORD *)v43 = 0;
  FilenameFromPathW = CommonUtil::UtilGetFilenameFromPathW(a5, v43, (const wchar_t **)&v45, v18);
  if ( FilenameFromPathW < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 34;
      goto LABEL_7;
    }
    goto LABEL_8;
  }
  *(_OWORD *)v32 = 0;
  MpCopyFileApiToStr((const wchar_t **)v32, a2);
  v19 = g_pcsAsimovLock;
  v20 = v22;
  if ( g_pcsAsimovLock )
  {
    CommonUtil::CMpCriticalSection::lock(g_pcsAsimovLock);
    if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
      && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 16LL) & 0x400000000000LL) != 0
      && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider
                                                                                               + 24LL) )
    {
      v23 = a6;
      v24 = a7;
      v34 = *(_QWORD *)v43;
      v35 = *(_QWORD *)v44;
      v36 = v32[0];
      v25 = *((_DWORD *)g_aAsimov + 18);
      v26 = *((_DWORD *)g_aAsimov + 17);
      v27 = *((_DWORD *)g_aAsimov + 16);
      v28 = *((unsigned __int8 *)g_aAsimov + 60);
      v29 = *((unsigned __int8 *)g_aAsimov + 59);
      v30 = *((unsigned __int8 *)g_aAsimov + 58);
      v31 = *((unsigned __int8 *)g_aAsimov + 57);
      LODWORD(v22) = *((unsigned __int8 *)g_aAsimov + 56);
      v37 = *((_QWORD *)g_aAsimov + 6);
      v38 = *((_QWORD *)g_aAsimov + 5);
      v39 = *((_QWORD *)g_aAsimov + 4);
      v40 = *((_QWORD *)g_aAsimov + 3);
      v41 = *((_QWORD *)g_aAsimov + 2);
      v42 = *((_QWORD *)g_aAsimov + 1);
      LOBYTE(v21) = a3;
      v33 = (__int64)v20;
      v32[0] = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
        g_hMpAsimovProvider,
        (int)&byte_140036433,
        (__int64)v32,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v24,
        (__int64)&v21,
        (__int64)&v23);
    }
    CommonUtil::CMpCriticalSection::unlock(v19);
  }
  if ( v20 )
    MpFreeMemory(v20);
  return 0;
}

```

## disassembly

```asm
0x14001f304  mov     [rsp-8+arg_10], rbx
0x14001f309  push    rbp
0x14001f30a  push    rsi
0x14001f30b  push    rdi
0x14001f30c  push    r14
0x14001f30e  push    r15
0x14001f310  lea     rbp, [rsp-40h]
0x14001f315  sub     rsp, 190h
0x14001f31c  mov     rax, cs:__security_cookie
0x14001f323  xor     rax, rsp
0x14001f326  mov     [rbp+60h+var_30], rax
0x14001f32a  mov     rsi, [rbp+60h+arg_20]
0x14001f331  mov     rdi, r9
0x14001f334  mov     r15d, r8d
0x14001f337  mov     r14d, edx
0x14001f33a  mov     rbx, rcx
0x14001f33d  call    rand
0x14001f342  mov     r9d, eax
0x14001f345  mov     eax, 51EB851Fh
0x14001f34a  imul    r9d
0x14001f34d  sar     edx, 5
0x14001f350  mov     ecx, edx
0x14001f352  shr     ecx, 1Fh
0x14001f355  add     edx, ecx
0x14001f357  imul    ecx, edx, 64h ; 'd'
0x14001f35a  cmp     r9d, ecx
0x14001f35d  jz      short loc_14001F369
0x14001f35f  mov     eax, 80004005h
0x14001f364  jmp     loc_14001F67D
0x14001f369  lea     rdx, [rbp+60h+var_D8]; wchar_t **
0x14001f36d  mov     [rbp+60h+var_D8], 0
0x14001f375  mov     rcx, rbx; unsigned int *
0x14001f378  call    ?GetClientProcessName@@YAJPEAXPEAPEA_W@Z; GetClientProcessName(void *,wchar_t * *)
0x14001f37d  mov     ebx, eax
0x14001f37f  test    eax, eax
0x14001f381  jns     short loc_14001F3D8
0x14001f383  mov     edx, eax
0x14001f385  lea     rcx, aFailedToGetCli; "Failed to get client process name, hr=%"...
0x14001f38c  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001f391  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f398  lea     rdx, WPP_GLOBAL_Control
0x14001f39f  cmp     rcx, rdx
0x14001f3a2  jz      short loc_14001F3C2
0x14001f3a4  test    byte ptr [rcx+1Ch], 1
0x14001f3a8  jz      short loc_14001F3C2
0x14001f3aa  mov     edx, 20h ; ' '
0x14001f3af  mov     rcx, [rcx+10h]
0x14001f3b3  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001f3ba  mov     r9d, ebx
0x14001f3bd  call    WPP_SF_d
0x14001f3c2  mov     rcx, [rbp+60h+var_D8]
0x14001f3c6  test    rcx, rcx
0x14001f3c9  jz      short loc_14001F3D1
0x14001f3cb  call    cs:__imp_MpFreeMemory
0x14001f3d1  mov     eax, ebx
0x14001f3d3  jmp     loc_14001F67D
0x14001f3d8  lea     r8, [rbp+60h+var_38]; wchar_t **
0x14001f3dc  mov     qword ptr [rbp+60h+var_40], 0
0x14001f3e4  lea     rdx, [rbp+60h+var_40]; wchar_t *
0x14001f3e8  mov     [rbp+60h+var_38], 0
0x14001f3f0  mov     rcx, rdi; this
0x14001f3f3  call    ?UtilGetFilenameFromPathW@CommonUtil@@YAJPEB_WPEAPEB_WPEA_K@Z; CommonUtil::UtilGetFilenameFromPathW(wchar_t const *,wchar_t const * *,unsigned __int64 *)
0x14001f3f8  mov     ebx, eax
0x14001f3fa  test    eax, eax
0x14001f3fc  jns     short loc_14001F41E
0x14001f3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f405  lea     rdx, WPP_GLOBAL_Control
0x14001f40c  cmp     rcx, rdx
0x14001f40f  jz      short loc_14001F3C2
0x14001f411  test    byte ptr [rcx+1Ch], 1
0x14001f415  jz      short loc_14001F3C2
0x14001f417  mov     edx, 21h ; '!'
0x14001f41c  jmp     short loc_14001F3AF
0x14001f41e  lea     r8, [rbp+60h+var_38]; wchar_t **
0x14001f422  mov     qword ptr [rbp+60h+var_48], 0
0x14001f42a  lea     rdx, [rbp+60h+var_48]; wchar_t *
0x14001f42e  mov     rcx, rsi; this
0x14001f431  call    ?UtilGetFilenameFromPathW@CommonUtil@@YAJPEB_WPEAPEB_WPEA_K@Z; CommonUtil::UtilGetFilenameFromPathW(wchar_t const *,wchar_t const * *,unsigned __int64 *)
0x14001f436  mov     ebx, eax
0x14001f438  test    eax, eax
0x14001f43a  jns     short loc_14001F467
0x14001f43c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f443  lea     rdx, WPP_GLOBAL_Control
0x14001f44a  cmp     rcx, rdx
0x14001f44d  jz      loc_14001F3C2
0x14001f453  test    byte ptr [rcx+1Ch], 1
0x14001f457  jz      loc_14001F3C2
0x14001f45d  mov     edx, 22h ; '"'
0x14001f462  jmp     loc_14001F3AF
0x14001f467  xorps   xmm0, xmm0
0x14001f46a  lea     rcx, [rbp+60h+var_A8]
0x14001f46e  mov     edx, r14d
0x14001f471  movups  xmmword ptr [rbp+60h+var_A8], xmm0
0x14001f475  call    MpCopyFileApiToStr
0x14001f47a  mov     rdi, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x14001f481  mov     rbx, [rbp+60h+var_D8]
0x14001f485  test    rdi, rdi
0x14001f488  jz      loc_14001F66D
0x14001f48e  mov     rcx, rdi; lpCriticalSection
0x14001f491  call    ?lock@CMpCriticalSection@CommonUtil@@QEBAXXZ; CommonUtil::CMpCriticalSection::lock(void)
0x14001f496  mov     r8, cs:g_hMpAsimovProvider
0x14001f49d  cmp     dword ptr [r8], 5
0x14001f4a1  jbe     loc_14001F665
0x14001f4a7  mov     rcx, 400000000000h
0x14001f4b1  test    [r8+10h], rcx
0x14001f4b5  jz      loc_14001F665
0x14001f4bb  mov     rax, [r8+18h]
0x14001f4bf  and     rax, rcx
0x14001f4c2  cmp     rax, [r8+18h]
0x14001f4c6  jnz     loc_14001F665
0x14001f4cc  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x14001f4d3  mov     eax, [rbp+60h+arg_28]
0x14001f4d9  mov     dword ptr [rbp+60h+var_D0], eax
0x14001f4dc  mov     eax, [rbp+60h+arg_30]
0x14001f4e2  mov     dword ptr [rbp+60h+var_D0+4], eax
0x14001f4e5  mov     rax, qword ptr [rbp+60h+var_48]
0x14001f4e9  mov     [rbp+60h+var_90], rax
0x14001f4ed  mov     rax, qword ptr [rbp+60h+var_40]
0x14001f4f1  mov     [rbp+60h+var_88], rax
0x14001f4f5  mov     rax, [rbp+60h+var_A8]
0x14001f4f9  mov     [rbp+60h+var_80], rax
0x14001f4fd  mov     eax, [rcx+48h]
0x14001f500  mov     dword ptr [rbp+60h+var_C8], eax
0x14001f503  mov     eax, [rcx+44h]
0x14001f506  mov     dword ptr [rbp+60h+var_C8+4], eax
0x14001f509  mov     eax, [rcx+40h]
0x14001f50c  mov     [rbp+60h+var_C0], eax
0x14001f50f  movzx   eax, byte ptr [rcx+3Ch]
0x14001f513  mov     [rbp+60h+var_BC], eax
0x14001f516  movzx   eax, byte ptr [rcx+3Bh]
0x14001f51a  mov     [rbp+60h+var_B8], eax
0x14001f51d  movzx   eax, byte ptr [rcx+3Ah]
0x14001f521  mov     [rbp+60h+var_B4], eax
0x14001f524  movzx   eax, byte ptr [rcx+39h]
0x14001f528  mov     [rbp+60h+var_B0], eax
0x14001f52b  movzx   eax, byte ptr [rcx+38h]
0x14001f52f  mov     dword ptr [rbp+60h+var_D8], eax
0x14001f532  mov     rax, [rcx+30h]
0x14001f536  mov     [rbp+60h+var_78], rax
0x14001f53a  mov     rax, [rcx+28h]
0x14001f53e  mov     [rbp+60h+var_70], rax
0x14001f542  mov     rax, [rcx+20h]
0x14001f546  mov     [rbp+60h+var_68], rax
0x14001f54a  mov     rax, [rcx+18h]
0x14001f54e  mov     [rbp+60h+var_60], rax
0x14001f552  mov     rax, [rcx+10h]
0x14001f556  mov     [rbp+60h+var_58], rax
0x14001f55a  mov     rax, [rcx+8]
0x14001f55e  mov     [rbp+60h+var_50], rax
0x14001f562  lea     rax, [rbp+60h+var_D0]
0x14001f566  mov     [rsp+1B0h+var_E8], rax; __int64
0x14001f56e  lea     rax, [rbp+60h+var_E0]
0x14001f572  mov     [rsp+1B0h+var_F0], rax; __int64
0x14001f57a  lea     rax, [rbp+60h+var_D0+4]
0x14001f57e  mov     [rsp+1B0h+var_F8], rax; __int64
0x14001f586  lea     rax, [rbp+60h+var_98]
0x14001f58a  mov     [rsp+1B0h+var_100], rax; __int64
0x14001f592  lea     rax, [rbp+60h+var_90]
0x14001f596  mov     [rsp+1B0h+var_108], rax; __int64
0x14001f59e  lea     rax, [rbp+60h+var_88]
0x14001f5a2  mov     [rsp+1B0h+var_110], rax; __int64
0x14001f5aa  lea     rax, [rbp+60h+var_80]
0x14001f5ae  mov     [rsp+1B0h+var_118], rax; __int64
0x14001f5b6  lea     rax, [rbp+60h+var_C8]
0x14001f5ba  mov     [rsp+1B0h+var_120], rax; __int64
0x14001f5c2  lea     rax, [rbp+60h+var_C8+4]
0x14001f5c6  mov     [rsp+1B0h+var_128], rax; __int64
0x14001f5ce  lea     rax, [rbp+60h+var_C0]
0x14001f5d2  mov     [rsp+1B0h+var_130], rax; __int64
0x14001f5da  lea     rax, [rbp+60h+var_BC]
0x14001f5de  mov     [rsp+1B0h+var_138], rax; __int64
0x14001f5e3  lea     rax, [rbp+60h+var_B8]
0x14001f5e7  mov     [rsp+1B0h+var_140], rax; __int64
0x14001f5ec  lea     rax, [rbp+60h+var_B4]
0x14001f5f0  mov     [rsp+1B0h+var_148], rax; __int64
0x14001f5f5  lea     rax, [rbp+60h+var_B0]
0x14001f5f9  mov     [rsp+1B0h+var_150], rax; __int64
0x14001f5fe  lea     rax, [rbp+60h+var_D8]
0x14001f602  mov     [rsp+1B0h+var_158], rax; __int64
0x14001f607  lea     rax, [rbp+60h+var_78]
0x14001f60b  mov     [rsp+1B0h+var_160], rax; __int64
0x14001f610  lea     rax, [rbp+60h+var_70]
0x14001f614  mov     [rsp+1B0h+var_168], rax; __int64
0x14001f619  lea     rax, [rbp+60h+var_68]
0x14001f61d  mov     [rsp+1B0h+var_170], rax; __int64
0x14001f622  lea     rax, [rbp+60h+var_60]
0x14001f626  mov     [rsp+1B0h+var_178], rax; __int64
0x14001f62b  lea     rax, [rbp+60h+var_58]
0x14001f62f  mov     byte ptr [rbp+60h+var_E0], r15b
0x14001f633  mov     [rbp+60h+var_98], rbx
0x14001f637  mov     [rbp+60h+var_A8], 2000000h
0x14001f63f  mov     [rsp+1B0h+var_180], rax; __int64
0x14001f644  lea     rdx, byte_140036433; int
0x14001f64b  lea     rax, [rbp+60h+var_50]
0x14001f64f  mov     rcx, r8; int
0x14001f652  mov     [rsp+1B0h+var_188], rax; __int64
0x14001f657  lea     rax, [rbp+60h+var_A8]
0x14001f65b  mov     [rsp+1B0h+var_190], rax; __int64
0x14001f660  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U2@U2@U2@U2@U3@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@555555544445AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x14001f665  mov     rcx, rdi; lpCriticalSection
0x14001f668  call    ?unlock@CMpCriticalSection@CommonUtil@@QEBAXXZ; CommonUtil::CMpCriticalSection::unlock(void)
0x14001f66d  test    rbx, rbx
0x14001f670  jz      short loc_14001F67B
0x14001f672  mov     rcx, rbx
0x14001f675  call    cs:__imp_MpFreeMemory
0x14001f67b  xor     eax, eax
0x14001f67d  mov     rcx, [rbp+60h+var_30]
0x14001f681  xor     rcx, rsp; StackCookie
0x14001f684  call    __security_check_cookie
0x14001f689  mov     rbx, [rsp+1B0h+arg_10]
0x14001f691  add     rsp, 190h
0x14001f698  pop     r15
0x14001f69a  pop     r14
0x14001f69c  pop     rdi
0x14001f69d  pop     rsi
0x14001f69e  pop     rbp
0x14001f69f  retn
```

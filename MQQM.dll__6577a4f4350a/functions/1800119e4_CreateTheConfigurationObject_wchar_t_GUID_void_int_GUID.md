# _CreateTheConfigurationObject(wchar_t *,_GUID *,void * *,int *,_GUID *)

- ea: `0x1800119e4`
- end: `0x180011f8e`
- name: `?_CreateTheConfigurationObject@@YAJPEA_WPEAU_GUID@@PEAPEAXPEAH1@Z`
- size: `1450`
- prototype: `__int64 __fastcall(wchar_t *, struct _GUID *, void **, int *, struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180011730`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x1800119e4`
- `0x180012920`
- `0x1800129cc`
- `0x18002c61c`
- `0x180094f00`
- `0x180094fd8`
- `0x18009bd1c`
- `0x1800d6e3e`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180011c69`
- `msvcrt!free` at `0x180011c73`
- `msvcrt!free` at `0x180011eb6`
- `msvcrt!free` at `0x180011ef0`
- `msvcrt!free` at `0x180011efa`
- `msvcrt!free` at `0x180011f1e`
- `msvcrt!free` at `0x180011f28`
- `msvcrt!free` at `0x180011f58`
- `msvcrt!free` at `0x180011f62`
- `msvcrt!free` at `0x180011c69`
- `msvcrt!free` at `0x180011c73`
- `msvcrt!free` at `0x180011eb6`
- `msvcrt!free` at `0x180011ef0`
- `msvcrt!free` at `0x180011efa`
- `msvcrt!free` at `0x180011f1e`
- `msvcrt!free` at `0x180011f28`
- `msvcrt!free` at `0x180011f58`
- `msvcrt!free` at `0x180011f62`
- `ADVAPI32!GetLengthSid` at `0x180011d72`
- `ADVAPI32!GetLengthSid` at `0x180011d72`
- `mqsec!GetFalconKeyValue` at `0x180011a84`
- `mqsec!GetFalconKeyValue` at `0x180011b0f`
- `mqsec!GetFalconKeyValue` at `0x180011ce0`
- `mqsec!GetFalconKeyValue` at `0x180011d2d`
- `mqsec!GetFalconKeyValue` at `0x180011a84`
- `mqsec!GetFalconKeyValue` at `0x180011b0f`
- `mqsec!GetFalconKeyValue` at `0x180011ce0`
- `mqsec!GetFalconKeyValue` at `0x180011d2d`
- `mqsec!MQSec_StorePubKeys` at `0x180011b80`
- `mqsec!MQSec_StorePubKeys` at `0x180011b80`

## string_xrefs

- `0x180011a7d`: `MachineCache\MQS_Routing`
- `0x180011cd9`: `setup\UserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _CreateTheConfigurationObject(wchar_t *a1, struct _GUID *a2, void **a3, int *a4, struct _GUID *a5)
{
  int v7; // r12d
  int FalconKeyValue; // eax
  signed int v9; // ebx
  unsigned __int16 v10; // r8
  int v12; // eax
  int v13; // eax
  BYTE *pBlobData; // rbx
  BYTE *v15; // rdi
  int v16; // eax
  int v17; // esi
  unsigned int v18; // ecx
  struct _GUID *v19; // rax
  int v20; // r13d
  __int64 v21; // rdx
  __int64 v22; // r8
  PVOID *v23; // rcx
  DWORD LengthSid; // eax
  DWORD v25; // esi
  void *v26; // rax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  wchar_t *v30; // r12
  int v31; // eax
  unsigned int v32; // r14d
  unsigned int v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v35; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v38; // [rsp+68h] [rbp-98h]
  int v39; // [rsp+70h] [rbp-90h] BYREF
  struct tagBLOB v40; // [rsp+78h] [rbp-88h] BYREF
  struct tagBLOB v41; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID *v42; // [rsp+98h] [rbp-68h] BYREF
  void **v43; // [rsp+A0h] [rbp-60h]
  struct _GUID *v44; // [rsp+A8h] [rbp-58h]
  BYTE *v45; // [rsp+B0h] [rbp-50h]
  BYTE *v46; // [rsp+B8h] [rbp-48h]
  _DWORD v47[12]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v48; // [rsp+F0h] [rbp-10h] BYREF
  int v49; // [rsp+F8h] [rbp-8h]
  __int16 v50; // [rsp+108h] [rbp+8h]
  char v51; // [rsp+110h] [rbp+10h]
  __int16 v52; // [rsp+120h] [rbp+20h]
  bool v53; // [rsp+128h] [rbp+28h]
  __int16 v54; // [rsp+138h] [rbp+38h]
  int v55; // [rsp+140h] [rbp+40h]
  __int16 v56; // [rsp+150h] [rbp+50h]
  char v57; // [rsp+158h] [rbp+58h]
  __int16 v58; // [rsp+168h] [rbp+68h]
  struct tagBLOB v59; // [rsp+170h] [rbp+70h]
  __int16 v60; // [rsp+180h] [rbp+80h]
  struct tagBLOB v61; // [rsp+188h] [rbp+88h]
  __int16 v62; // [rsp+198h] [rbp+98h]
  unsigned int v63; // [rsp+1A0h] [rbp+A0h]
  void *v64; // [rsp+1A8h] [rbp+A8h]
  __int16 v65; // [rsp+1B0h] [rbp+B0h]
  DWORD v66; // [rsp+1B8h] [rbp+B8h]
  _BYTE *v67; // [rsp+1C0h] [rbp+C0h]
  _BYTE pSid[256]; // [rsp+1E0h] [rbp+E0h] BYREF

  v43 = a3;
  v44 = a2;
  v38 = a1;
  v47[0] = 230;
  v48 = 19;
  v7 = 0;
  v49 = 0;
  v47[1] = 228;
  v50 = 17;
  v51 = 0;
  v37 = 0;
  v33 = 4;
  v34 = 4;
  FalconKeyValue = GetFalconKeyValue(L"MachineCache\\MQS_Routing", &v34, &v37, &v33, 0);
  v9 = FalconKeyValue;
  if ( FalconKeyValue )
  {
    if ( FalconKeyValue > 0 )
      v9 = (unsigned __int16)FalconKeyValue | 0x80070000;
    if ( v9 >= 0 )
      return (unsigned int)v9;
    v10 = 205;
LABEL_6:
    LogMsgHR(v9, (wchar_t *)L"qm/creatobj", v10);
    return (unsigned int)v9;
  }
  v47[2] = 227;
  v52 = 17;
  v53 = v37 != 0;
  if ( v37 == 1 )
    v49 = 1;
  v36 = 0;
  v39 = 768;
  v34 = 4;
  v33 = 4;
  v12 = GetFalconKeyValue(L"setup\\OSType", &v34, &v36, &v33, (const wchar_t *)&v39);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    if ( v9 >= 0 )
      return (unsigned int)v9;
    v10 = 210;
    goto LABEL_6;
  }
  v47[3] = 220;
  v54 = 19;
  v55 = v36;
  v47[4] = 229;
  v56 = 17;
  v57 = 0;
  *a4 = 0;
  *(_QWORD *)&v40.cbSize = 0;
  v40.pBlobData = 0;
  *(_QWORD *)&v41.cbSize = 0;
  v41.pBlobData = 0;
  v13 = MQSec_StorePubKeys(0, 0, &v40, &v41);
  v9 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids,
        (unsigned int)v13);
    v10 = 490;
    goto LABEL_6;
  }
  pBlobData = v40.pBlobData;
  v45 = v40.pBlobData;
  v15 = v41.pBlobData;
  v46 = v41.pBlobData;
  v47[5] = 238;
  v58 = 65;
  v59 = v40;
  v47[6] = 239;
  v60 = 65;
  v61 = v41;
  v35 = 0;
  v42 = 0;
  v16 = ADGetComputerSites(a1, &v35, &v42);
  v17 = v16;
  if ( v16 < 0 )
  {
    LogMsgHR(v16, (wchar_t *)L"qm/creatobj", 0xBEu);
    LogMsgHR(v17, (wchar_t *)L"qm/creatobj", 0xDCu);
    free(v15);
    free(pBlobData);
    return (unsigned int)v17;
  }
  v18 = v35;
  v19 = v42;
  if ( v35 )
    *a5 = *v42;
  v47[7] = 222;
  v62 = 4168;
  v64 = v19;
  v63 = v18;
  v34 = 3;
  v33 = 256;
  if ( !GetFalconKeyValue(L"setup\\UserSid", &v34, pSid, &v33, 0) )
  {
    LengthSid = GetLengthSid(pSid);
    v47[8] = 241;
    v65 = 65;
    v67 = pSid;
    v66 = LengthSid;
    v7 = 8;
    v20 = 9;
    if ( v43 )
    {
      v25 = LengthSid;
      v26 = MmAllocate(LengthSid);
      *v43 = v26;
      memcpy_0(v26, pSid, v25);
    }
    goto LABEL_32;
  }
  v20 = 8;
  v35 = 0;
  v33 = 4;
  if ( !GetFalconKeyValue(L"setup\\LocalUser", &v34, &v35, &v33, 0) && v35 == 1 )
  {
LABEL_32:
    v23 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_33;
  }
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_36;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids);
    goto LABEL_32;
  }
LABEL_33:
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 4) != 0 )
    WPP_SF_Dd(v23[2], 19, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids, v37, v36);
LABEL_36:
  v27 = ADCreateObject(1, v21, v22, v38, 0, v20, v47, &v48, v44);
  v17 = v27;
  if ( v27 < 0 && v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids,
        (unsigned int)v27);
    v30 = v38;
    v17 = ADCreateObject(1, v28, v29, v38, 0, v20 - 1, v47, &v48, v44);
  }
  else
  {
    v30 = v38;
  }
  free(v64);
  if ( v17 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids);
    free(v15);
    free(pBlobData);
  }
  else
  {
    if ( v17 == -1072823025 )
    {
      v31 = _VerifyComputerObject(v30);
      v32 = v31;
      if ( v31 < 0 )
      {
        LogMsgHR(v31, (wchar_t *)L"qm/creatobj", 0x17Cu);
        free(v15);
        free(pBlobData);
        return v32;
      }
    }
    LogMsgHR(v17, (wchar_t *)L"qm/creatobj", 0xE6u);
    free(v15);
    free(pBlobData);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800119e4  push    rbp
0x1800119e6  push    rbx
0x1800119e7  push    rsi
0x1800119e8  push    rdi
0x1800119e9  push    r12
0x1800119eb  push    r13
0x1800119ed  push    r14
0x1800119ef  push    r15
0x1800119f1  lea     rbp, [rsp-1F8h]
0x1800119f9  sub     rsp, 2F8h
0x180011a00  mov     rax, cs:__security_cookie
0x180011a07  xor     rax, rsp
0x180011a0a  mov     [rbp+230h+var_50], rax
0x180011a11  mov     rdi, r9
0x180011a14  mov     [rbp+230h+var_290], r8
0x180011a18  mov     [rbp+230h+var_288], rdx
0x180011a1c  mov     rsi, rcx
0x180011a1f  mov     [rsp+330h+var_2C8], rcx
0x180011a24  mov     r14, [rbp+230h+arg_20]
0x180011a2b  mov     [rbp+230h+var_270], 0E6h
0x180011a32  mov     eax, 13h
0x180011a37  mov     [rbp+230h+var_240], ax
0x180011a3b  xor     r12d, r12d
0x180011a3e  mov     [rbp+230h+var_238], r12d
0x180011a42  mov     [rbp+230h+var_26C], 0E4h
0x180011a49  lea     r13d, [rax-2]
0x180011a4d  mov     [rbp+230h+var_228], r13w
0x180011a52  mov     [rbp+230h+var_220], r12b
0x180011a56  mov     [rsp+330h+var_2D0], r12d
0x180011a5b  lea     r15d, [rax-0Fh]
0x180011a5f  mov     [rsp+330h+var_2E0], r15d
0x180011a64  mov     [rsp+330h+var_2DC], r15d
0x180011a69  mov     [rsp+330h+var_310], r12
0x180011a6e  lea     r9, [rsp+330h+var_2E0]
0x180011a73  lea     r8, [rsp+330h+var_2D0]
0x180011a78  lea     rdx, [rsp+330h+var_2DC]
0x180011a7d  lea     rcx, aMachinecacheMq; "MachineCache\\MQS_Routing"
0x180011a84  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180011a8a  mov     ebx, eax
0x180011a8c  test    eax, eax
0x180011a8e  jz      short loc_180011ABA
0x180011a90  jle     short loc_180011A9B
0x180011a92  movzx   ebx, ax
0x180011a95  or      ebx, 80070000h
0x180011a9b  test    ebx, ebx
0x180011a9d  jns     short loc_180011AB3
0x180011a9f  mov     r8d, 0CDh; unsigned __int16
0x180011aa5  lea     rdx, aQmCreatobj; "qm/creatobj"
0x180011aac  mov     ecx, ebx; int
0x180011aae  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011ab3  mov     eax, ebx
0x180011ab5  jmp     loc_180011F6B
0x180011aba  mov     [rbp+230h+var_268], 0E3h
0x180011ac1  mov     [rbp+230h+var_210], r13w
0x180011ac6  mov     eax, [rsp+330h+var_2D0]
0x180011aca  test    eax, eax
0x180011acc  setnz   [rbp+230h+var_208]
0x180011ad0  cmp     eax, 1
0x180011ad3  jnz     short loc_180011AD8
0x180011ad5  mov     [rbp+230h+var_238], eax
0x180011ad8  mov     [rsp+330h+var_2D4], r12d
0x180011add  mov     [rsp+330h+var_2C0], 300h
0x180011ae5  mov     [rsp+330h+var_2DC], r15d
0x180011aea  mov     [rsp+330h+var_2E0], r15d
0x180011aef  lea     rax, [rsp+330h+var_2C0]
0x180011af4  mov     [rsp+330h+var_310], rax
0x180011af9  lea     r9, [rsp+330h+var_2E0]
0x180011afe  lea     r8, [rsp+330h+var_2D4]
0x180011b03  lea     rdx, [rsp+330h+var_2DC]
0x180011b08  lea     rcx, aSetupOstype; "setup\\OSType"
0x180011b0f  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180011b15  mov     ebx, eax
0x180011b17  test    eax, eax
0x180011b19  jz      short loc_180011B35
0x180011b1b  jle     short loc_180011B26
0x180011b1d  movzx   ebx, ax
0x180011b20  or      ebx, 80070000h
0x180011b26  test    ebx, ebx
0x180011b28  jns     short loc_180011AB3
0x180011b2a  mov     r8d, 0D2h
0x180011b30  jmp     loc_180011AA5
0x180011b35  mov     r15d, 0DCh
0x180011b3b  mov     [rbp+230h+var_264], r15d
0x180011b3f  mov     eax, 13h
0x180011b44  mov     [rbp+230h+var_1F8], ax
0x180011b48  mov     eax, [rsp+330h+var_2D4]
0x180011b4c  mov     [rbp+230h+var_1F0], eax
0x180011b4f  mov     [rbp+230h+var_260], 0E5h
0x180011b56  mov     [rbp+230h+var_1E0], r13w
0x180011b5b  mov     [rbp+230h+var_1D8], r12b
0x180011b5f  mov     [rdi], r12d
0x180011b62  mov     [rsp+330h+var_2B8], r12
0x180011b67  mov     [rbp+230h+var_2B0], r12
0x180011b6b  mov     [rbp+230h+var_2A8], r12
0x180011b6f  mov     [rbp+230h+Block], r12
0x180011b73  lea     r9, [rbp+230h+var_2A8]
0x180011b77  lea     r8, [rsp+330h+var_2B8]
0x180011b7c  xor     edx, edx
0x180011b7e  xor     ecx, ecx
0x180011b80  call    cs:__imp_?MQSec_StorePubKeys@@YAJHHPEAUtagBLOB@@0@Z; MQSec_StorePubKeys(int,int,tagBLOB *,tagBLOB *)
0x180011b86  mov     ebx, eax
0x180011b88  test    eax, eax
0x180011b8a  jns     short loc_180011BC6
0x180011b8c  lea     r14, WPP_GLOBAL_Control
0x180011b93  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b9a  cmp     rcx, r14
0x180011b9d  jz      short loc_180011BBB
0x180011b9f  test    byte ptr [rcx+1Ch], 1
0x180011ba3  jz      short loc_180011BBB
0x180011ba5  mov     edx, r13d
0x180011ba8  mov     r9d, eax
0x180011bab  lea     r8, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids
0x180011bb2  mov     rcx, [rcx+10h]
0x180011bb6  call    WPP_SF_d
0x180011bbb  mov     r8d, 1EAh
0x180011bc1  jmp     loc_180011AA5
0x180011bc6  mov     rbx, [rbp+230h+var_2B0]
0x180011bca  mov     [rbp+230h+var_280], rbx
0x180011bce  mov     rdi, [rbp+230h+Block]
0x180011bd2  mov     [rbp+230h+var_278], rdi
0x180011bd6  mov     [rbp+230h+var_25C], 0EEh
0x180011bdd  mov     r13d, 41h ; 'A'
0x180011be3  mov     [rbp+230h+var_1C8], r13w
0x180011be8  mov     eax, dword ptr [rsp+330h+var_2B8]
0x180011bec  mov     dword ptr [rbp+230h+var_1C0], eax
0x180011bef  mov     eax, dword ptr [rsp+330h+var_2B8+4]
0x180011bf3  mov     dword ptr [rbp+230h+var_1C0+4], eax
0x180011bf6  mov     [rbp+230h+var_1B8], rbx
0x180011bfa  mov     [rbp+230h+var_258], 0EFh
0x180011c01  mov     [rbp+230h+var_1B0], r13w
0x180011c09  mov     eax, dword ptr [rbp+230h+var_2A8]
0x180011c0c  mov     dword ptr [rbp+230h+var_1A8], eax
0x180011c12  mov     eax, dword ptr [rbp+230h+var_2A8+4]
0x180011c15  mov     dword ptr [rbp+230h+var_1A8+4], eax
0x180011c1b  mov     [rbp+230h+var_1A0], rdi
0x180011c22  mov     [rsp+330h+var_2D8], r12d
0x180011c27  mov     [rbp+230h+var_298], r12
0x180011c2b  lea     r8, [rbp+230h+var_298]; struct _GUID **
0x180011c2f  lea     rdx, [rsp+330h+var_2D8]; unsigned int *
0x180011c34  mov     rcx, rsi; wchar_t *
0x180011c37  call    ?ADGetComputerSites@@YAJPEB_WPEAKPEAPEAU_GUID@@@Z; ADGetComputerSites(wchar_t const *,ulong *,_GUID * *)
0x180011c3c  mov     esi, eax
0x180011c3e  test    eax, eax
0x180011c40  jns     short loc_180011C7F
0x180011c42  lea     r8d, [r13+7Dh]; unsigned __int16
0x180011c46  lea     rdx, aQmCreatobj; "qm/creatobj"
0x180011c4d  mov     ecx, eax; int
0x180011c4f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011c54  mov     r8d, r15d; unsigned __int16
0x180011c57  lea     rdx, aQmCreatobj; "qm/creatobj"
0x180011c5e  mov     ecx, esi; int
0x180011c60  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011c65  nop
0x180011c66  mov     rcx, rdi; Block
0x180011c69  call    cs:__imp_free
0x180011c6f  nop
0x180011c70  mov     rcx, rbx; Block
0x180011c73  call    cs:__imp_free
0x180011c79  nop
0x180011c7a  jmp     loc_180011F69
0x180011c7f  mov     ecx, [rsp+330h+var_2D8]
0x180011c83  mov     rax, [rbp+230h+var_298]
0x180011c87  test    ecx, ecx
0x180011c89  jz      short loc_180011C93
0x180011c8b  movups  xmm0, xmmword ptr [rax]
0x180011c8e  movdqu  xmmword ptr [r14], xmm0
0x180011c93  mov     [rbp+230h+var_254], 0DEh
0x180011c9a  mov     edx, 1048h
0x180011c9f  mov     [rbp+230h+var_198], dx
0x180011ca6  mov     [rbp+230h+var_188], rax
0x180011cad  mov     [rbp+230h+var_190], ecx
0x180011cb3  mov     [rsp+330h+var_2DC], 3
0x180011cbb  mov     [rsp+330h+var_2E0], 100h
0x180011cc3  mov     [rsp+330h+var_310], r12
0x180011cc8  lea     r9, [rsp+330h+var_2E0]
0x180011ccd  lea     r8, [rbp+230h+pSid]
0x180011cd4  lea     rdx, [rsp+330h+var_2DC]
0x180011cd9  lea     rcx, aSetupUsersid; "setup\\UserSid"
0x180011ce0  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180011ce6  lea     r15, WPP_f3280b8dd5f934f498a6d0101b3d1c6c_Traceguids
0x180011ced  lea     r14, WPP_GLOBAL_Control
0x180011cf4  test    eax, eax
0x180011cf6  jz      short loc_180011D6B
0x180011cf8  mov     r13d, 8
0x180011cfe  mov     [rsp+330h+var_2D8], 0
0x180011d06  mov     [rsp+330h+var_2E0], 4
0x180011d0e  mov     [rsp+330h+var_310], 0
0x180011d17  lea     r9, [rsp+330h+var_2E0]
0x180011d1c  lea     r8, [rsp+330h+var_2D8]
0x180011d21  lea     rdx, [rsp+330h+var_2DC]
0x180011d26  lea     rcx, aSetupLocaluser; "setup\\LocalUser"
0x180011d2d  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180011d33  test    eax, eax
0x180011d35  jnz     short loc_180011D42
0x180011d37  cmp     [rsp+330h+var_2D8], 1
0x180011d3c  jz      loc_180011DCF
0x180011d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d49  cmp     rcx, r14
0x180011d4c  jz      loc_180011DFF
0x180011d52  test    byte ptr [rcx+1Ch], 2
0x180011d56  jz      short loc_180011DD6
0x180011d58  mov     edx, 12h
0x180011d5d  mov     r8, r15
0x180011d60  mov     rcx, [rcx+10h]
0x180011d64  call    WPP_SF_
0x180011d69  jmp     short loc_180011DCF
0x180011d6b  lea     rcx, [rbp+230h+pSid]; pSid
0x180011d72  call    cs:__imp_GetLengthSid
0x180011d78  mov     [rbp+230h+var_250], 0F1h
0x180011d7f  mov     [rbp+230h+var_180], r13w
0x180011d87  lea     rcx, [rbp+230h+pSid]
0x180011d8e  mov     [rbp+230h+var_170], rcx
0x180011d95  mov     [rbp+230h+var_178], eax
0x180011d9b  mov     r12d, 8
0x180011da1  lea     r13d, [r12+1]
0x180011da6  cmp     [rbp+230h+var_290], 0
0x180011dab  jz      short loc_180011DCF
0x180011dad  mov     esi, eax
0x180011daf  mov     ecx, eax; unsigned __int64
0x180011db1  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180011db6  mov     rcx, [rbp+230h+var_290]
0x180011dba  mov     [rcx], rax
0x180011dbd  mov     r8d, esi; Size
0x180011dc0  lea     rdx, [rbp+230h+pSid]; Src
0x180011dc7  mov     rcx, rax; void *
0x180011dca  call    memcpy_0
0x180011dcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dd6  cmp     rcx, r14
0x180011dd9  jz      short loc_180011DFF
0x180011ddb  test    byte ptr [rcx+1Ch], 4
0x180011ddf  jz      short loc_180011DFF
0x180011de1  mov     edx, 13h
0x180011de6  mov     eax, [rsp+330h+var_2D4]
0x180011dea  mov     dword ptr [rsp+330h+var_310], eax
0x180011dee  mov     r9d, [rsp+330h+var_2D0]
0x180011df3  mov     r8, r15
0x180011df6  mov     rcx, [rcx+10h]
0x180011dfa  call    WPP_SF_Dd
0x180011dff  mov     rax, [rbp+230h+var_288]
0x180011e03  mov     [rsp+330h+var_2F0], rax
0x180011e08  lea     rax, [rbp+230h+var_240]
0x180011e0c  mov     [rsp+330h+var_2F8], rax
0x180011e11  lea     rax, [rbp+230h+var_270]
0x180011e15  mov     [rsp+330h+var_300], rax
0x180011e1a  mov     [rsp+330h+var_308], r13d
0x180011e1f  mov     [rsp+330h+var_310], 0
0x180011e28  mov     r9, [rsp+330h+var_2C8]
0x180011e2d  mov     ecx, 1
0x180011e32  call    ?ADCreateObject@@YAJW4AD_OBJECT@@PEB_W_N1PEAXKQEBKQEBUtagPROPVARIANT@@PEAU_GUID@@@Z; ADCreateObject(AD_OBJECT,wchar_t const *,bool,wchar_t const *,void *,ulong,ulong const * const,tagPROPVARIANT const * const,_GUID *)
0x180011e37  mov     esi, eax
0x180011e39  test    eax, eax
0x180011e3b  jns     short loc_180011EAA
0x180011e3d  test    r12d, r12d
0x180011e40  jz      short loc_180011EAA
0x180011e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e49  cmp     rcx, r14
0x180011e4c  jz      short loc_180011E68
0x180011e4e  test    byte ptr [rcx+1Ch], 4
0x180011e52  jz      short loc_180011E68
0x180011e54  mov     edx, 14h
0x180011e59  mov     r9d, eax
0x180011e5c  mov     r8, r15
0x180011e5f  mov     rcx, [rcx+10h]
0x180011e63  call    WPP_SF_d
0x180011e68  lea     eax, [r13-1]
0x180011e6c  mov     rcx, [rbp+230h+var_288]
0x180011e70  mov     [rsp+330h+var_2F0], rcx
0x180011e75  lea     rcx, [rbp+230h+var_240]
0x180011e79  mov     [rsp+330h+var_2F8], rcx
0x180011e7e  lea     rcx, [rbp+230h+var_270]
0x180011e82  mov     [rsp+330h+var_300], rcx
0x180011e87  mov     [rsp+330h+var_308], eax
0x180011e8b  mov     [rsp+330h+var_310], 0
0x180011e94  mov     r12, [rsp+330h+var_2C8]
0x180011e99  mov     r9, r12
0x180011e9c  mov     ecx, 1
0x180011ea1  call    ?ADCreateObject@@YAJW4AD_OBJECT@@PEB_W_N1PEAXKQEBKQEBUtagPROPVARIANT@@PEAU_GUID@@@Z; ADCreateObject(AD_OBJECT,wchar_t const *,bool,wchar_t const *,void *,ulong,ulong const * const,tagPROPVARIANT const * const,_GUID *)
0x180011ea6  mov     esi, eax
0x180011ea8  jmp     short loc_180011EAF
0x180011eaa  mov     r12, [rsp+330h+var_2C8]
0x180011eaf  mov     rcx, [rbp+230h+var_188]; Block
0x180011eb6  call    cs:__imp_free
0x180011ebc  nop
0x180011ebd  test    esi, esi
0x180011ebf  jns     short loc_180011F31
0x180011ec1  cmp     esi, 0C00E050Fh
0x180011ec7  jnz     short loc_180011F06
0x180011ec9  mov     rcx, r12; wchar_t *
0x180011ecc  call    ?_VerifyComputerObject@@YAJPEB_W@Z; _VerifyComputerObject(wchar_t const *)
0x180011ed1  mov     r14d, eax
0x180011ed4  test    eax, eax
0x180011ed6  jns     short loc_180011F06
0x180011ed8  mov     r8d, 17Ch; unsigned __int16
0x180011ede  lea     rdx, aQmCreatobj; "qm/creatobj"
0x180011ee5  mov     ecx, eax; int
0x180011ee7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180011eec  nop
0x180011eed  mov     rcx, rdi; Block
0x180011ef0  call    cs:__imp_free
0x180011ef6  nop
  ... truncated ...
```

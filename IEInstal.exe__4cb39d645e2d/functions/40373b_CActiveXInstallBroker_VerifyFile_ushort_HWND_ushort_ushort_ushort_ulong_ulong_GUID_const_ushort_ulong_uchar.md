# CActiveXInstallBroker::VerifyFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ulong,ulong,_GUID const &,ushort * *,ulong *,uchar * *)

- ea: `0x40373b`
- end: `0x403d7e`
- name: `?VerifyFile@CActiveXInstallBroker@@QAGJPAGPAUHWND__@@000KKABU_GUID@@PAPAGPAKPAPAE@Z`
- size: `1603`
- prototype: `int __userpurge@<eax>(const unsigned __int16 *@<edx>, int@<ecx>, CActiveXInstallBroker *this, unsigned __int16 *, HWND, unsigned __int16 *, __int64, _DWORD *, unsigned __int16 **, struct _GUID *, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x405d10`

## callees

- `0x4026e7`
- `0x402eb9`
- `0x402ed3`
- `0x40301a`
- `0x40373b`
- `0x406e47`
- `0x4072e3`
- `0x407c3c`
- `0x407d14`
- `0x407eab`
- `0x408301`
- `0x408480`
- `0x408a2f`
- `0x408c6e`
- `0x408fe0`
- `0x40cb60`
- `0x40d1d0`
- `0x40eb27`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x403d41`
- `KERNEL32!CloseHandle` at `0x403d41`
- `KERNEL32!CreateFileW` at `0x403a64`
- `KERNEL32!CreateFileW` at `0x403a64`
- `KERNEL32!GetLastError` at `0x403a73`
- `KERNEL32!GetLastError` at `0x403a73`
- `ole32!CoTaskMemAlloc` at `0x40390a`
- `ole32!CoTaskMemAlloc` at `0x4039a5`
- `ole32!CoTaskMemAlloc` at `0x40390a`
- `ole32!CoTaskMemAlloc` at `0x4039a5`
- `OLEAUT32!__imp__SysFreeString@4` at `0x403cf7`
- `OLEAUT32!__imp__SysFreeString@4` at `0x403cf7`
- `OLEAUT32!__imp__SysStringLen@4` at `0x403b1d`
- `OLEAUT32!__imp__SysStringLen@4` at `0x403b1d`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::VerifyFile@<eax>(
        const unsigned __int16 *a1@<edx>,
        int a2@<ecx>,
        CActiveXInstallBroker *this,
        unsigned __int16 *a4,
        HWND a5,
        unsigned __int16 *a6,
        __int64 a7,
        _DWORD *a8,
        unsigned __int16 **a9,
        struct _GUID *a10,
        unsigned __int16 **a11,
        unsigned int *a12,
        unsigned __int8 **a13)
{
  BSTR *v14; // esi
  _DWORD *v15; // edi
  signed int HasExtensionW; // ebx
  int v17; // eax
  bool v18; // zf
  char v19; // bl
  void *v20; // eax
  void *v21; // eax
  signed int LastError; // eax
  _DWORD *v23; // eax
  _DWORD **v24; // edi
  int v25; // eax
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  _DWORD *v29; // edi
  struct _GUID v31; // [esp-24h] [ebp-1BCh]
  struct _GUID v32; // [esp-24h] [ebp-1BCh]
  struct _GUID v33; // [esp-24h] [ebp-1BCh]
  unsigned __int16 *v34; // [esp+0h] [ebp-198h]
  void *v35; // [esp+4h] [ebp-194h]
  unsigned __int16 **v36; // [esp+4h] [ebp-194h]
  char v37; // [esp+12h] [ebp-186h]
  char v38; // [esp+12h] [ebp-186h]
  char v39; // [esp+13h] [ebp-185h]
  _DWORD **v41; // [esp+18h] [ebp-180h]
  HWND hObject; // [esp+20h] [ebp-178h]
  _DWORD *v43; // [esp+24h] [ebp-174h]
  unsigned int v44; // [esp+34h] [ebp-164h] BYREF
  int v45; // [esp+38h] [ebp-160h]
  int v46; // [esp+3Ch] [ebp-15Ch]
  int v47; // [esp+40h] [ebp-158h]
  unsigned int v48; // [esp+44h] [ebp-154h]
  struct _GUID *v49; // [esp+48h] [ebp-150h]
  unsigned __int16 **v50; // [esp+4Ch] [ebp-14Ch]
  int v51; // [esp+50h] [ebp-148h]
  int v52; // [esp+54h] [ebp-144h]
  int v53; // [esp+58h] [ebp-140h]
  unsigned int v54; // [esp+5Ch] [ebp-13Ch]
  unsigned __int16 v55[154]; // [esp+60h] [ebp-138h] BYREF

  v14 = a9;
  v49 = a10;
  v50 = a11;
  hObject = 0;
  v45 = -736211171;
  v46 = 298951687;
  v47 = -1073690229;
  v48 = 1091216207;
  v51 = 11191659;
  v52 = 298896708;
  v53 = -1073692020;
  v54 = -292175281;
  v44 = 0;
  v41 = 0;
  memset(v55, 0, 300);
  v15 = (_DWORD *)a2;
  if ( !CLock::Lock((CLock *)a2) )
  {
    HasExtensionW = -2147024882;
    goto LABEL_72;
  }
  if ( *(int *)(a2 + 28) < 1 )
  {
    HasExtensionW = -2147019873;
    goto LABEL_72;
  }
  if ( !a1 || !a5 || !a9 )
  {
    HasExtensionW = -2147024809;
LABEL_72:
    if ( !a9 )
      goto LABEL_77;
    goto LABEL_76;
  }
  v17 = wcscmp(a1, *(const unsigned __int16 **)(a2 + 36));
  if ( v17 )
    v17 = v17 < 0 ? -1 : 1;
  if ( v17 )
    goto LABEL_11;
  v18 = *(_DWORD *)(a2 + 84) == 0;
  *(_DWORD *)v55 = 40;
  *(_DWORD *)&v55[16] = 0;
  *(_DWORD *)&v55[6] = 0;
  *(_DWORD *)&v55[4] = a4;
  *(_DWORD *)&v55[2] = v44;
  if ( v18 )
  {
    v39 = 1;
    v37 = 1;
  }
  else
  {
    if ( g_fRunningAsSystem )
    {
      HasExtensionW = CActiveXInstallBroker::CallSystemInstallerVerifyFile((CActiveXInstallBroker *)a2, a4, a9);
      if ( HasExtensionW < 0 )
        goto LABEL_76;
      HasExtensionW = AxiPreScanPathW(v34);
      if ( HasExtensionW < 0 )
        goto LABEL_76;
      HasExtensionW = VerifyFileHasExtensionW(v34);
      if ( HasExtensionW < 0 )
        goto LABEL_76;
      v19 = 0;
      v39 = 0;
      v37 = 0;
      *(_DWORD *)&v55[10] = 60;
      v20 = CoTaskMemAlloc(0x3Cu);
      *(_DWORD *)&v55[8] = v20;
      if ( v20 )
      {
        memset(v20, 0, *(size_t *)&v55[10]);
        **(_DWORD **)&v55[8] = *(_DWORD *)&v55[10];
        *(_DWORD *)(*(_DWORD *)&v55[8] + 8) = 1;
      }
      else
      {
        *(_DWORD *)&v55[8] = 0;
      }
    }
    else
    {
      v39 = 1;
      if ( *(_DWORD *)(a2 + 88) )
      {
        HasExtensionW = CActiveXInstallBroker::CallSystemInstallerVerifyFile((CActiveXInstallBroker *)a2, a4, a9);
        if ( HasExtensionW < 0 )
          goto LABEL_76;
        HasExtensionW = AxiPreScanPathW(v34);
        if ( HasExtensionW < 0 )
          goto LABEL_76;
        HasExtensionW = VerifyFileHasExtensionW(v34);
        if ( HasExtensionW < 0 )
          goto LABEL_76;
        *(_DWORD *)&v55[18] = 1;
        v19 = 0;
      }
      else
      {
        v19 = 1;
      }
      v37 = v19;
    }
    *(_DWORD *)&v55[10] = 60;
    v21 = CoTaskMemAlloc(0x3Cu);
    *(_DWORD *)&v55[8] = v21;
    if ( v21 )
    {
      memset(v21, 0, *(size_t *)&v55[10]);
      **(_DWORD **)&v55[8] = *(_DWORD *)&v55[10];
      *(_DWORD *)(*(_DWORD *)&v55[8] + 8) = 1;
    }
    else
    {
      *(_DWORD *)&v55[8] = 0;
      *(_DWORD *)&v55[10] = 0;
    }
    if ( !v19 )
      goto LABEL_42;
  }
  HasExtensionW = CreateRandomDir((char *)v34, (unsigned int)v35);
  if ( HasExtensionW < 0 )
    goto LABEL_76;
  HasExtensionW = CopyFileToRandomDir((const char *)a9, v34, v36);
  if ( HasExtensionW < 0 )
    goto LABEL_76;
  HasExtensionW = AxiPreScanPathW(v34);
  if ( HasExtensionW < 0 )
    goto LABEL_76;
  HasExtensionW = VerifyFileHasExtensionW(v34);
  if ( HasExtensionW < 0 )
    goto LABEL_76;
  hObject = (HWND)CreateFileW(*a9, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( hObject == HWND_MESSAGE|0x2 )
  {
    LastError = GetLastError();
    HasExtensionW = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      HasExtensionW = LastError;
    goto LABEL_76;
  }
  v19 = v37;
LABEL_42:
  v38 = v19;
  if ( !v39 )
    goto LABEL_53;
  v23 = operator new(0x10u);
  v24 = (_DWORD **)v23;
  v43 = v23;
  if ( !v23 )
  {
    v41 = 0;
    HasExtensionW = -2147024882;
    goto LABEL_75;
  }
  *v23 = &CActiveXInstallSecurityManager::`vftable';
  v23[1] = 1;
  v23[3] = 0;
  v23[2] = 0;
  HasExtensionW = CActiveXInstallSecurityManager::Initialize((CActiveXInstallSecurityManager *)v23, a4);
  v41 = v24;
  if ( HasExtensionW < 0 )
  {
LABEL_75:
    v15 = (_DWORD *)a2;
    goto LABEL_76;
  }
  HasExtensionW = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, unsigned int *))**v24)(
                    **v24,
                    v24,
                    &IID_IInternetHostSecurityManager,
                    &v44);
  v41 = v24;
  if ( HasExtensionW < 0 )
  {
    v14 = a9;
    goto LABEL_75;
  }
  if ( a6 && SysStringLen(a6) )
  {
    v41 = v24;
    v19 = v38;
    *(_QWORD *)v31.Data4 = a7;
    *(_DWORD *)&v31.Data2 = a6;
    v14 = a9;
    v31.Data1 = (unsigned int)*a9;
    if ( VerifyTrust(
           hObject,
           v31,
           v55,
           (void *)v51,
           (unsigned __int16 *)v52,
           (unsigned __int16 *)v53,
           v54,
           (unsigned int)v34,
           v35) >= 0 )
    {
      v15 = (_DWORD *)a2;
      goto LABEL_53;
    }
    *(_QWORD *)v32.Data4 = a7;
    *(_DWORD *)&v32.Data2 = a6;
    v14 = a9;
    v32.Data1 = (unsigned int)*a9;
    HasExtensionW = VerifyTrust(
                      hObject,
                      v32,
                      v55,
                      (void *)v45,
                      (unsigned __int16 *)v46,
                      (unsigned __int16 *)v47,
                      v48,
                      (unsigned int)v34,
                      v35);
    v15 = (_DWORD *)a2;
    v41 = (_DWORD **)v43;
    if ( HasExtensionW < 0 )
    {
      v41 = (_DWORD **)v43;
      goto LABEL_76;
    }
  }
  else
  {
    *(_QWORD *)v33.Data4 = a7;
    v14 = a9;
    *(_QWORD *)&v33.Data1 = (unsigned int)*a9;
    HasExtensionW = VerifyTrust(
                      hObject,
                      v33,
                      v55,
                      (void *)v45,
                      (unsigned __int16 *)v46,
                      (unsigned __int16 *)v47,
                      v48,
                      (unsigned int)v34,
                      v35);
    v15 = (_DWORD *)a2;
    v41 = (_DWORD **)v43;
    if ( HasExtensionW < 0 )
      goto LABEL_76;
  }
  v19 = v38;
LABEL_53:
  if ( !v15[21] && !ContainingPathIsTamperProof(v34) )
  {
LABEL_11:
    HasExtensionW = -2147024891;
LABEL_76:
    SysFreeString(*v14);
    *v14 = 0;
    goto LABEL_77;
  }
  if ( v19 )
  {
    HasExtensionW = CopyFileToTempDir((const char *)v34, (unsigned __int16 **)v35);
    if ( HasExtensionW < 0 )
      goto LABEL_76;
  }
  HasExtensionW = AddToFileListW(v34, (struct sFNAME **)v35);
  if ( HasExtensionW < 0 )
    goto LABEL_76;
  v25 = *(_DWORD *)&v55[8];
  if ( *(_DWORD *)&v55[8] && *(_DWORD *)&v55[10] )
  {
    v26 = *(_DWORD *)(*(_DWORD *)&v55[8] + 20);
    if ( v26 )
      *(_DWORD *)(*(_DWORD *)&v55[8] + 20) = v26 - *(_DWORD *)&v55[8];
    v27 = *(_DWORD *)(v25 + 28);
    if ( v27 )
      *(_DWORD *)(v25 + 28) = v27 - v25;
    v28 = *(_DWORD *)(v25 + 36);
    if ( v28 )
      *(_DWORD *)(v25 + 36) = v28 - v25;
    v49->Data1 = *(_DWORD *)&v55[10];
    *v50 = *(unsigned __int16 **)&v55[8];
  }
  else
  {
    v49->Data1 = 0;
    *v50 = 0;
  }
  v29 = v15 + 12;
  *v29++ = *a8;
  *v29++ = a8[1];
  *v29 = a8[2];
  v29[1] = a8[3];
  v15 = (_DWORD *)a2;
  *(_DWORD *)(a2 + 28) = 2;
LABEL_77:
  if ( v44 )
    (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)v44 + 8))(*(_DWORD *)(*(_DWORD *)v44 + 8), v44);
  if ( v41 )
    ((void (__thiscall *)(_DWORD, _DWORD **))(*v41)[2])((*v41)[2], v41);
  if ( hObject && hObject != HWND_MESSAGE|0x2 )
    CloseHandle(hObject);
  if ( HasExtensionW >= 0 )
    v15[22] = 0;
  RemoveDirectoryAndChildren((const char *)v34);
  CLock::Unlock((CLock *)v15);
  return HasExtensionW;
}

```

## disassembly

```asm
0x40373b  mov     edi, edi
0x40373d  push    ebp
0x40373e  mov     ebp, esp
0x403740  and     esp, 0FFFFFFF8h
0x403743  sub     esp, 18Ch
0x403749  mov     eax, ___security_cookie
0x40374e  xor     eax, esp
0x403750  mov     [esp+18Ch+var_4], eax
0x403757  push    ebx
0x403758  push    esi; struct sFNAME **
0x403759  push    edi; char *
0x40375a  mov     ebx, edx
0x40375c  mov     [esp+198h+var_184], ecx
0x403760  mov     eax, [ebp+this]
0x403763  mov     [esp+198h+var_168], eax
0x403767  mov     eax, [ebp+arg_4]
0x40376a  mov     [esp+198h+var_17C], eax
0x40376e  mov     eax, [ebp+arg_8]
0x403771  mov     [esp+198h+var_174], eax
0x403775  mov     eax, [ebp+arg_C]
0x403778  xor     edx, edx
0x40377a  mov     esi, [ebp+arg_1C]
0x40377d  mov     [esp+198h+pbstr], eax
0x403781  mov     eax, [ebp+arg_20]
0x403784  mov     [esp+198h+var_150], eax
0x403788  mov     eax, [ebp+arg_24]
0x40378b  push    104h; Size
0x403790  mov     [esp+19Ch+var_14C], eax
0x403794  lea     eax, [esp+19Ch+var_110]
0x40379b  push    edx; Val
0x40379c  push    eax; void *
0x40379d  mov     [esp+1A4h+var_170], esi
0x4037a1  mov     [esp+1A4h+hObject], edx
0x4037a5  mov     [esp+1A4h+var_160], 0D41E4F1Dh
0x4037ad  mov     [esp+1A4h+var_15C], 11D1A407h
0x4037b5  mov     [esp+1A4h+var_158], 0C000C98Bh
0x4037bd  mov     [esp+1A4h+var_154], 410AA34Fh
0x4037c5  mov     [esp+1A4h+var_148], 0AAC56Bh
0x4037cd  mov     [esp+1A4h+var_144], 11D0CD44h
0x4037d5  mov     [esp+1A4h+var_140], 0C000C28Ch
0x4037dd  mov     [esp+1A4h+var_13C], 0EE95C24Fh
0x4037e5  mov     [esp+1A4h+var_164], edx
0x4037e9  mov     [esp+1A4h+var_180], edx
0x4037ed  call    _memset
0x4037f2  add     esp, 0Ch
0x4037f5  lea     edi, [esp+198h+var_138]
0x4037f9  xor     eax, eax
0x4037fb  push    0Ah
0x4037fd  pop     ecx
0x4037fe  rep stosd
0x403800  mov     edi, [esp+198h+var_184]
0x403804  mov     ecx, edi; this
0x403806  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x40380b  test    eax, eax
0x40380d  jnz     short loc_403819
0x40380f  mov     ebx, 8007000Eh
0x403814  jmp     loc_403CE7
0x403819  cmp     dword ptr [edi+1Ch], 1
0x40381d  jge     short loc_403829
0x40381f  mov     ebx, 8007139Fh
0x403824  jmp     loc_403CE7
0x403829  test    ebx, ebx
0x40382b  jz      loc_403CE2
0x403831  cmp     [esp+198h+var_174], 0
0x403836  jz      loc_403CE2
0x40383c  test    esi, esi
0x40383e  jz      loc_403CE2
0x403844  mov     eax, [edi+24h]
0x403847  mov     cx, [ebx]
0x40384a  cmp     cx, [eax]
0x40384d  jnz     short loc_40386D
0x40384f  test    cx, cx
0x403852  jz      short loc_403869
0x403854  mov     cx, [ebx+2]
0x403858  cmp     cx, [eax+2]
0x40385c  jnz     short loc_40386D
0x40385e  add     ebx, 4
0x403861  add     eax, 4
0x403864  test    cx, cx
0x403867  jnz     short loc_403847
0x403869  xor     eax, eax
0x40386b  jmp     short loc_403872
0x40386d  sbb     eax, eax
0x40386f  or      eax, 1
0x403872  test    eax, eax
0x403874  jz      short loc_403880
0x403876  mov     ebx, 80070005h
0x40387b  jmp     loc_403CF5
0x403880  cmp     dword ptr [edi+54h], 0
0x403884  mov     ecx, [esp+198h+var_17C]
0x403888  mov     eax, [esp+198h+var_164]
0x40388c  mov     dword ptr [esp+198h+var_138], 28h ; '('
0x403894  mov     [esp+198h+var_118], 0
0x40389f  mov     [esp+198h+var_12C], 0
0x4038a7  mov     [esp+198h+var_130], ecx
0x4038ab  mov     [esp+198h+var_134], eax
0x4038af  jz      loc_4039F3
0x4038b5  cmp     ?g_fRunningAsSystem@@3HA, 0; int g_fRunningAsSystem
0x4038bc  jz      loc_403948
0x4038c2  push    esi; unsigned __int16 **
0x4038c3  push    ecx; unsigned __int16 *
0x4038c4  mov     ecx, edi; this
0x4038c6  call    ?CallSystemInstallerVerifyFile@CActiveXInstallBroker@@AAEJPAGPAPAG@Z; CActiveXInstallBroker::CallSystemInstallerVerifyFile(ushort *,ushort * *)
0x4038cb  mov     ebx, eax
0x4038cd  test    ebx, ebx
0x4038cf  js      loc_403CF5
0x4038d5  mov     ecx, [esi]
0x4038d7  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x4038dc  mov     ebx, eax
0x4038de  test    ebx, ebx
0x4038e0  js      loc_403CF5
0x4038e6  mov     ecx, [esi]
0x4038e8  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x4038ed  mov     ebx, eax
0x4038ef  test    ebx, ebx
0x4038f1  js      loc_403CF5
0x4038f7  push    3Ch ; '<'
0x4038f9  pop     eax
0x4038fa  xor     bl, bl
0x4038fc  mov     [esp+198h+var_185], 0
0x403901  push    eax; cb
0x403902  mov     [esp+19Ch+var_186], bl
0x403906  mov     [esp+19Ch+Size], eax
0x40390a  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x403910  mov     [esp+198h+var_128], eax
0x403914  test    eax, eax
0x403916  jz      short loc_40393E
0x403918  push    [esp+198h+Size]; Size
0x40391c  push    0; Val
0x40391e  push    eax; void *
0x40391f  call    _memset
0x403924  mov     ecx, [esp+1A4h+var_128]
0x403928  add     esp, 0Ch
0x40392b  mov     eax, [esp+198h+Size]
0x40392f  mov     [ecx], eax
0x403931  mov     eax, [esp+198h+var_128]
0x403935  mov     dword ptr [eax+8], 1
0x40393c  jmp     short loc_40399D
0x40393e  mov     [esp+198h+var_128], 0
0x403946  jmp     short loc_40399D
0x403948  cmp     dword ptr [edi+58h], 0
0x40394c  mov     [esp+198h+var_185], 1
0x403951  jz      short loc_403997
0x403953  push    esi; unsigned __int16 **
0x403954  push    ecx; unsigned __int16 *
0x403955  mov     ecx, edi; this
0x403957  call    ?CallSystemInstallerVerifyFile@CActiveXInstallBroker@@AAEJPAGPAPAG@Z; CActiveXInstallBroker::CallSystemInstallerVerifyFile(ushort *,ushort * *)
0x40395c  mov     ebx, eax
0x40395e  test    ebx, ebx
0x403960  js      loc_403CF5
0x403966  mov     ecx, [esi]
0x403968  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x40396d  mov     ebx, eax
0x40396f  test    ebx, ebx
0x403971  js      loc_403CF5
0x403977  mov     ecx, [esi]
0x403979  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x40397e  mov     ebx, eax
0x403980  test    ebx, ebx
0x403982  js      loc_403CF5
0x403988  mov     [esp+198h+var_114], 1
0x403993  xor     bl, bl
0x403995  jmp     short loc_403999
0x403997  mov     bl, 1
0x403999  mov     [esp+198h+var_186], bl
0x40399d  push    3Ch ; '<'
0x40399f  pop     ecx
0x4039a0  push    ecx; cb
0x4039a1  mov     [esp+19Ch+Size], ecx
0x4039a5  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x4039ab  mov     [esp+198h+var_128], eax
0x4039af  test    eax, eax
0x4039b1  jz      short loc_4039D9
0x4039b3  push    [esp+198h+Size]; Size
0x4039b7  push    0; Val
0x4039b9  push    eax; void *
0x4039ba  call    _memset
0x4039bf  mov     ecx, [esp+1A4h+var_128]
0x4039c3  add     esp, 0Ch
0x4039c6  mov     eax, [esp+198h+Size]
0x4039ca  mov     [ecx], eax
0x4039cc  mov     eax, [esp+198h+var_128]
0x4039d0  mov     dword ptr [eax+8], 1
0x4039d7  jmp     short loc_4039E9
0x4039d9  mov     [esp+198h+var_128], 0
0x4039e1  mov     [esp+198h+Size], 0
0x4039e9  test    bl, bl
0x4039eb  jz      loc_403A90
0x4039f1  jmp     short loc_4039FD
0x4039f3  mov     [esp+198h+var_185], 1
0x4039f8  mov     [esp+198h+var_186], 1
0x4039fd  lea     ecx, [esp+198h+var_110]
0x403a04  call    ?CreateRandomDir@@YGJPADK@Z; CreateRandomDir(char *,ulong)
0x403a09  mov     ebx, eax
0x403a0b  test    ebx, ebx
0x403a0d  js      loc_403CF5
0x403a13  mov     edx, [esp+198h+var_174]
0x403a17  lea     ecx, [esp+198h+var_110]
0x403a1e  push    esi; char *
0x403a1f  call    ?CopyFileToRandomDir@@YGJPBDPAGPAPAG@Z; CopyFileToRandomDir(char const *,ushort *,ushort * *)
0x403a24  mov     ebx, eax
0x403a26  test    ebx, ebx
0x403a28  js      loc_403CF5
0x403a2e  mov     ecx, [esi]
0x403a30  call    ?AxiPreScanPathW@@YGJPBG@Z; AxiPreScanPathW(ushort const *)
0x403a35  mov     ebx, eax
0x403a37  test    ebx, ebx
0x403a39  js      loc_403CF5
0x403a3f  mov     ecx, [esi]
0x403a41  call    ?VerifyFileHasExtensionW@@YGJPBG@Z; VerifyFileHasExtensionW(ushort const *)
0x403a46  mov     ebx, eax
0x403a48  test    ebx, ebx
0x403a4a  js      loc_403CF5
0x403a50  push    0; hTemplateFile
0x403a52  push    80h; dwFlagsAndAttributes
0x403a57  push    3; dwCreationDisposition
0x403a59  push    0; void *
0x403a5b  push    1; dwShareMode
0x403a5d  push    80000000h; dwDesiredAccess
0x403a62  push    dword ptr [esi]; lpFileName
0x403a64  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x403a6a  mov     [esp+198h+hObject], eax
0x403a6e  cmp     eax, 0FFFFFFFFh
0x403a71  jnz     short loc_403A8C
0x403a73  call    ds:__imp__GetLastError@0; GetLastError()
0x403a79  movzx   ebx, ax
0x403a7c  or      ebx, 80070000h
0x403a82  test    eax, eax
0x403a84  cmovle  ebx, eax
0x403a87  jmp     loc_403CF5
0x403a8c  mov     bl, [esp+198h+var_186]
0x403a90  cmp     [esp+198h+var_185], 0
0x403a95  mov     [esp+198h+var_186], bl
0x403a99  jz      loc_403C17
0x403a9f  push    10h; dwBytes
0x403aa1  call    ??2@YAPAXI@Z; operator new(uint)
0x403aa6  mov     edi, eax
0x403aa8  mov     [esp+19Ch+var_174], edi
0x403aac  pop     ecx
0x403aad  test    edi, edi
0x403aaf  jz      loc_403CA1
0x403ab5  push    [esp+198h+var_17C]; unsigned __int16 *
0x403ab9  mov     ecx, edi; this
0x403abb  mov     dword ptr [edi], offset ??_7CActiveXInstallSecurityManager@@6B@; const CActiveXInstallSecurityManager::`vftable'
0x403ac1  mov     dword ptr [edi+4], 1
0x403ac8  mov     dword ptr [edi+0Ch], 0
0x403acf  mov     dword ptr [edi+8], 0
0x403ad6  call    ?Initialize@CActiveXInstallSecurityManager@@QAEJPAG@Z; CActiveXInstallSecurityManager::Initialize(ushort *)
0x403adb  mov     ebx, eax
0x403add  mov     [esp+198h+var_180], edi
0x403ae1  test    ebx, ebx
0x403ae3  js      loc_403CF1
0x403ae9  mov     eax, [edi]
0x403aeb  mov     esi, [eax]
0x403aed  lea     eax, [esp+198h+var_164]
0x403af1  push    eax; unsigned int
0x403af2  push    offset _IID_IInternetHostSecurityManager; unsigned __int16 *
0x403af7  push    edi; unsigned __int16 *
0x403af8  mov     ecx, esi
0x403afa  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x403b00  call    esi
0x403b02  mov     ebx, eax
0x403b04  mov     [esp+198h+var_180], edi
0x403b08  test    ebx, ebx
0x403b0a  js      loc_403CED
0x403b10  mov     eax, [esp+198h+pbstr]
0x403b14  test    eax, eax
0x403b16  jz      loc_403BC4
0x403b1c  push    eax; unsigned int
0x403b1d  call    ds:__imp__SysStringLen@4; SysStringLen(x)
0x403b23  test    eax, eax
0x403b25  jz      loc_403BC4
0x403b2b  sub     esp, 10h
0x403b2e  mov     [esp+1A8h+var_180], edi
0x403b32  mov     edi, esp
0x403b34  mov     edx, [esp+1A8h+var_17C]
0x403b38  mov     ecx, [esp+1A8h+var_168]
0x403b3c  lea     esi, [esp+1A8h+var_148]
0x403b40  mov     bl, [esp+1A8h+var_186]
0x403b44  lea     eax, [esp+1A8h+var_138]
0x403b48  push    eax; unsigned __int16 *
0x403b49  push    dword ptr [ebp+arg_10+4]
0x403b4c  movsd
0x403b4d  push    dword ptr [ebp+arg_10]
0x403b50  push    [esp+1B4h+pbstr]
0x403b54  movsd
0x403b55  movsd
0x403b56  movsd
0x403b57  mov     esi, [esp+1B8h+var_170]
0x403b5b  push    dword ptr [esi]; struct _GUID
0x403b5d  push    [esp+1BCh+hObject]; HWND
0x403b61  call    ?VerifyTrust@@YGJPAUHWND__@@U_GUID@@PAGPAX22KK3@Z; VerifyTrust(HWND__ *,_GUID,ushort *,void *,ushort *,ushort *,ulong,ulong,void *)
0x403b66  test    eax, eax
0x403b68  jns     loc_403CAE
0x403b6e  sub     esp, 10h
0x403b71  mov     edx, [esp+1A8h+var_17C]
0x403b75  mov     edi, esp
0x403b77  mov     ecx, [esp+1A8h+var_168]
0x403b7b  lea     esi, [esp+1A8h+var_160]
0x403b7f  lea     eax, [esp+1A8h+var_138]
  ... truncated ...
```

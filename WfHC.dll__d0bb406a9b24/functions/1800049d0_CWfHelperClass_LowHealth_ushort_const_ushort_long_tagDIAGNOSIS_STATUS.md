# CWfHelperClass::LowHealth(ushort const *,ushort * *,long *,tagDIAGNOSIS_STATUS *)

- ea: `0x1800049d0`
- end: `0x18000579c`
- name: `?LowHealth@CWfHelperClass@@UEAAJPEBGPEAPEAGPEAJPEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `3532`
- prototype: `__int64 __fastcall(CWfHelperClass *__hidden this, const unsigned __int16 *, unsigned __int16 **, int *, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800049d0`
- `0x180006560`
- `0x180006830`
- `0x180007ae0`
- `0x180007b40`
- `0x180007c80`
- `0x180007d60`
- `0x180008040`
- `0x1800082b0`
- `0x180008320`
- `0x180008440`
- `0x1800086f0`
- `0x18000c572`
- `0x18000c57e`
- `0x18000c5b0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004b0b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004b0b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004a75`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004a75`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004aba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004aba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004dab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004b9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004bd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004d95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004dab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800052dc`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180005149`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180005149`
- `FirewallAPI!FwFree` at `0x1800054a3`
- `FirewallAPI!FwFree` at `0x1800054a3`
- `FirewallAPI!FwAlloc` at `0x18000546d`
- `FirewallAPI!FwAlloc` at `0x18000546d`
- `FirewallAPI!FWFreeFirewallRules` at `0x180005540`
- `FirewallAPI!FWFreeFirewallRules` at `0x180005558`
- `FirewallAPI!FWFreeFirewallRules` at `0x180005607`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000561b`
- `FirewallAPI!FWFreeFirewallRules` at `0x180005540`
- `FirewallAPI!FWFreeFirewallRules` at `0x180005558`
- `FirewallAPI!FWFreeFirewallRules` at `0x180005607`
- `FirewallAPI!FWFreeFirewallRules` at `0x18000561b`
- `fwpuclnt!FwpmFreeMemory0` at `0x180005528`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800055f3`
- `fwpuclnt!FwpmFreeMemory0` at `0x180005528`
- `fwpuclnt!FwpmFreeMemory0` at `0x1800055f3`

## string_xrefs

- `0x180004cae`: `serviceid`
- `0x180004f68`: `protocol`

## pseudocode

```c
__int64 __fastcall CWfHelperClass::LowHealth(
        CWfHelperClass *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        int *a4,
        enum tagDIAGNOSIS_STATUS *a5)
{
  int v5; // eax
  int *v6; // r12
  unsigned __int16 **v7; // r11
  unsigned int v9; // esi
  int v10; // ebx
  HRESULT v11; // r14d
  HRESULT v12; // r12d
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 result; // rax
  enum tagDIAGNOSIS_STATUS *v20; // rdx
  __int64 v21; // rsi
  unsigned int v22; // r15d
  unsigned int v23; // ebx
  const wchar_t *v24; // rcx
  unsigned int v25; // ebx
  const wchar_t *v26; // rcx
  unsigned int v27; // ebx
  const wchar_t *v28; // rcx
  unsigned int v29; // ebx
  unsigned int v30; // r12d
  __int64 v31; // r14
  unsigned int v32; // r15d
  unsigned int v33; // ebx
  __int64 v34; // r14
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int128 v41; // xmm1
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  unsigned int v49; // r15d
  unsigned int v50; // ebx
  __int64 v51; // r14
  void *v52; // rbx
  BOOL valid; // eax
  void *v54; // rcx
  __int64 v55; // rsi
  unsigned int v56; // r15d
  unsigned int v57; // ebx
  const wchar_t *v58; // rcx
  unsigned int v59; // r15d
  unsigned int v60; // ebx
  const wchar_t *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rax
  LPVOID v64; // rax
  void *v65; // rcx
  LPVOID *v66; // rcx
  __int128 *v67; // rax
  __int64 v68; // rdx
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  __int128 v72; // xmm1
  __int128 v73; // xmm0
  __int128 v74; // xmm1
  __int128 v75; // xmm0
  __int128 v76; // xmm1
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  void *v79; // rax
  int v80; // r14d
  int v81; // ecx
  int v82; // r13d
  _QWORD *v83; // rdx
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rax
  int v87; // ecx
  __int64 v88; // rdx
  __int64 v89; // r9
  int v90; // eax
  int v91; // ecx
  int v92; // r8d
  int v93; // r10d
  unsigned int v94; // edx
  const unsigned __int16 *v95; // r9
  unsigned __int8 ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v97; // [rsp+28h] [rbp-D8h]
  int v98; // [rsp+30h] [rbp-D0h] BYREF
  enum tagDIAGNOSIS_STATUS *v99; // [rsp+38h] [rbp-C8h]
  unsigned __int16 **v100; // [rsp+40h] [rbp-C0h]
  LPVOID v101; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v102; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v103[33]; // [rsp+60h] [rbp-A0h] BYREF
  void *v104; // [rsp+168h] [rbp+68h]
  __int64 v105; // [rsp+170h] [rbp+70h]
  __int64 v106; // [rsp+178h] [rbp+78h]
  LPVOID v107; // [rsp+180h] [rbp+80h]
  LPVOID pv[2]; // [rsp+190h] [rbp+90h] BYREF
  LPVOID v109[2]; // [rsp+1A0h] [rbp+A0h]
  __int128 v110; // [rsp+1B0h] [rbp+B0h]
  __int128 v111; // [rsp+1C0h] [rbp+C0h]
  __int128 v112; // [rsp+1D0h] [rbp+D0h]
  __int128 v113; // [rsp+1E0h] [rbp+E0h]
  __int128 v114; // [rsp+1F0h] [rbp+F0h]
  __int128 v115; // [rsp+200h] [rbp+100h]
  __int128 v116; // [rsp+210h] [rbp+110h]
  void *p[2]; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int128 v118; // [rsp+2D8h] [rbp+1D8h]
  __int64 v119; // [rsp+2E8h] [rbp+1E8h]

  v5 = *((_DWORD *)this + 46);
  v6 = 0;
  *a3 = 0;
  v7 = a3;
  v100 = a3;
  *a5 = DS_REJECTED;
  v99 = a5;
  if ( !*((_DWORD *)this + 38) )
    goto LABEL_39;
  v9 = 0;
  if ( !*((_DWORD *)this + 45) )
  {
    if ( *((_DWORD *)this + 39) )
    {
      if ( (v5 & 2) == 0 )
      {
        v101 = 0;
        v98 = 0;
        v10 = 0;
        v11 = CoInitializeEx(0, 0);
        if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147417850 )
        {
          v12 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &v101);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v101 + 104LL))(v101, &v98);
            if ( v12 >= 0 && (v98 & 0x770) != 0 )
              v10 = 1;
          }
        }
        else
        {
          v12 = v11;
        }
        if ( v101 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v101 + 16LL))(v101);
        if ( v11 >= 0 )
          CoUninitialize();
        if ( v12 >= 0 && v10 )
        {
          v13 = *((_QWORD *)this + 18);
          *(_OWORD *)pv = 0;
          *(_OWORD *)v109 = 0;
          v110 = 0;
          v111 = 0;
          v112 = 0;
          v113 = 0;
          v114 = 0;
          v115 = 0;
          v116 = 0;
          if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v13 + 32LL))(
                 v13,
                 L"HasReproRootCauseFound",
                 pv) < 0 )
            goto LABEL_24;
          v14 = (int)v109[0];
          CoTaskMemFree(pv[0]);
          pv[0] = 0;
          if ( LODWORD(pv[1]) == 10 )
          {
            CoTaskMemFree(v109[0]);
            v109[0] = 0;
          }
          else if ( LODWORD(pv[1]) == 14 )
          {
            CoTaskMemFree(v109[1]);
            v109[1] = 0;
          }
          LODWORD(pv[1]) = 0;
          if ( !v14 )
          {
LABEL_24:
            v15 = *((_QWORD *)this + 18);
            *((_QWORD *)&v102 + 1) = 1;
            *(_QWORD *)&v102 = L"HasReproRootCauseFound";
            memset((char *)v103 + 4, 0, 124);
            LODWORD(v103[0]) = 1;
            v9 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v15 + 24LL))(v15, &v102);
            if ( (v9 & 0x80000000) == 0 )
              CWfHelperClass::WriteToNdfEtw(this, 2, L"Set HasReproRootCauseFound to TRUE");
            *((_DWORD *)this + 43) = 1;
            *((_OWORD *)this + 8) = RCG_FW_NEEDS_REPRO;
            *a5 = DS_CONFIRMED;
            goto LABEL_146;
          }
        }
LABEL_38:
        v20 = a5;
LABEL_148:
        v7 = v100;
        goto LABEL_149;
      }
LABEL_157:
      v20 = a5;
LABEL_149:
      if ( *v20 == DS_CONFIRMED )
      {
        *v7 = 0;
        v88 = 0;
        while ( 1 )
        {
          v89 = 20 * v88;
          if ( *((_DWORD *)qword_1800159E0 + 5 * v88) == *((_DWORD *)this + 32) )
          {
            v90 = *((_DWORD *)this + 33);
            if ( *(_DWORD *)((char *)qword_1800159E0 + v89 + 4) == v90 )
            {
              v91 = *((_DWORD *)this + 34);
              if ( *(_DWORD *)((char *)&qword_1800159E0[1] + v89) == v91 )
              {
                v92 = *((_DWORD *)this + 35);
                if ( *(_DWORD *)((char *)&qword_1800159E0[1] + v89 + 4) == v92 )
                  break;
              }
            }
          }
          v88 = (unsigned int)(v88 + 1);
          if ( (unsigned int)v88 >= 7 )
            return v9;
        }
        v93 = *(_DWORD *)((char *)&qword_1800159E0[2] + v89);
        if ( v93 != -1 )
        {
          v94 = *((_DWORD *)this + 32);
          if ( v94 == -799506376 && v90 == 1225616378 && v91 == 2035060623 && v92 == 1168137946
            || (v95 = (const unsigned __int16 *)&qword_1800117E0, v94 == 1504230422)
            && *((_DWORD *)this + 33) == 1127238400
            && v91 == -1392077145
            && v92 == -147431002 )
          {
            v95 = *(const unsigned __int16 **)(*((_QWORD *)this + 20) + 16LL);
          }
          UtilAssembleStringsWithAlloc(v7, v94, (const unsigned __int16 *)(unsigned __int16)v93, v95, ppv, v97);
        }
      }
      return v9;
    }
LABEL_39:
    *(_OWORD *)pv = 0;
    *(_OWORD *)v109 = 0;
    v110 = 0;
    v111 = 0;
    v112 = 0;
    v113 = 0;
    v114 = 0;
    v115 = 0;
    v116 = 0;
    memset_0(&v102, 0, 0x138u);
    v21 = *((_QWORD *)this + 4);
    if ( v21 )
    {
      v22 = *((_DWORD *)this + 6);
      v23 = 0;
      if ( v22 )
      {
        while ( 1 )
        {
          v24 = *(const wchar_t **)(v21 + 144LL * v23);
          if ( v24 )
          {
            if ( !wcsncmp_0(v24, L"providerguid", 0xFFu) )
              break;
          }
          if ( ++v23 >= v22 )
            goto LABEL_47;
        }
        if ( *(_DWORD *)(v21 + 144LL * v23 + 8) == 11 )
          *(_QWORD *)&v102 = v21 + 16 + 144LL * v23;
      }
LABEL_47:
      v25 = 0;
      if ( v22 )
      {
        while ( 1 )
        {
          v26 = *(const wchar_t **)(v21 + 144LL * v25);
          if ( v26 )
          {
            if ( !wcsncmp_0(v26, L"timestamp", 0xFFu) )
              break;
          }
          if ( ++v25 >= v22 )
            goto LABEL_54;
        }
        if ( *(_DWORD *)(v21 + 144LL * v25 + 16) == 8 )
          *((_QWORD *)&v102 + 1) = *(_QWORD *)(v21 + 144LL * v25 + 24);
      }
LABEL_54:
      v27 = 0;
      if ( v22 )
      {
        while ( 1 )
        {
          v28 = *(const wchar_t **)(v21 + 144LL * v27);
          if ( v28 )
          {
            if ( !wcsncmp_0(v28, L"protocol", 0xFFu) )
              break;
          }
          if ( ++v27 >= v22 )
            goto LABEL_61;
        }
        if ( *(_DWORD *)(v21 + 144LL * v27 + 8) == 7 )
          LOBYTE(v103[0]) = *(_BYTE *)(v21 + 144LL * v27 + 16);
      }
LABEL_61:
      v29 = 0;
      v30 = *((_DWORD *)this + 6);
      if ( v30 )
      {
        while ( 1 )
        {
          v31 = v21 + 144LL * v29;
          if ( *(_QWORD *)v31 )
          {
            if ( !wcsncmp_0(*(const wchar_t **)v31, L"localaddr", 0xFFu) )
              break;
          }
          if ( ++v29 >= v30 )
            goto LABEL_65;
        }
        v6 = 0;
        if ( *(_DWORD *)(v31 + 8) == 13 )
        {
          v35 = *(_OWORD *)(v31 + 32);
          *(_OWORD *)&v103[1] = *(_OWORD *)(v31 + 16);
          v36 = *(_OWORD *)(v31 + 48);
          *(_OWORD *)&v103[3] = v35;
          v37 = *(_OWORD *)(v31 + 64);
          *(_OWORD *)&v103[5] = v36;
          v38 = *(_OWORD *)(v31 + 80);
          *(_OWORD *)&v103[7] = v37;
          v39 = *(_OWORD *)(v31 + 96);
          *(_OWORD *)&v103[9] = v38;
          v40 = *(_OWORD *)(v31 + 112);
          *(_OWORD *)&v103[11] = v39;
          v41 = *(_OWORD *)(v31 + 128);
          *(_OWORD *)&v103[13] = v40;
          *(_OWORD *)&v103[15] = v41;
        }
      }
      else
      {
LABEL_65:
        v6 = 0;
      }
      v32 = *((_DWORD *)this + 6);
      v33 = 0;
      if ( v32 )
      {
        while ( 1 )
        {
          v34 = v21 + 144LL * v33;
          if ( *(_QWORD *)v34 )
          {
            if ( !wcsncmp_0(*(const wchar_t **)v34, L"remoteaddr", 0xFFu) )
              break;
          }
          if ( ++v33 >= v32 )
            goto LABEL_75;
        }
        if ( *(_DWORD *)(v34 + 8) == 13 )
        {
          v42 = *(_OWORD *)(v34 + 32);
          *(_OWORD *)&v103[17] = *(_OWORD *)(v34 + 16);
          v43 = *(_OWORD *)(v34 + 48);
          *(_OWORD *)&v103[19] = v42;
          v44 = *(_OWORD *)(v34 + 64);
          *(_OWORD *)&v103[21] = v43;
          v45 = *(_OWORD *)(v34 + 80);
          *(_OWORD *)&v103[23] = v44;
          v46 = *(_OWORD *)(v34 + 96);
          *(_OWORD *)&v103[25] = v45;
          v47 = *(_OWORD *)(v34 + 112);
          *(_OWORD *)&v103[27] = v46;
          v48 = *(_OWORD *)(v34 + 128);
          *(_OWORD *)&v103[29] = v47;
          *(_OWORD *)&v103[31] = v48;
        }
      }
LABEL_75:
      v49 = *((_DWORD *)this + 6);
      v50 = 0;
      if ( v49 )
      {
        while ( 1 )
        {
          v51 = v21 + 144LL * v50;
          if ( *(_QWORD *)v51 )
          {
            if ( !wcsncmp_0(*(const wchar_t **)v51, L"userid", 0xFFu) )
              break;
          }
          if ( ++v50 >= v49 )
            goto LABEL_85;
        }
        if ( *(_DWORD *)(v51 + 8) == 14 && *(_DWORD *)(v51 + 16) )
        {
          v52 = *(void **)(v51 + 24);
          valid = IsValidSid(v52);
          v54 = v104;
          if ( valid )
            v54 = v52;
          v104 = v54;
        }
      }
    }
LABEL_85:
    v55 = *((_QWORD *)this + 4);
    if ( v55 )
    {
      v56 = *((_DWORD *)this + 6);
      v57 = 0;
      if ( v56 )
      {
        while ( 1 )
        {
          v58 = *(const wchar_t **)(v55 + 144LL * v57);
          if ( v58 )
          {
            if ( !wcsncmp_0(v58, L"appid", 0xFFu) )
              break;
          }
          if ( ++v57 >= v56 )
            goto LABEL_93;
        }
        if ( *(_DWORD *)(v55 + 144LL * v57 + 8) == 10 )
          v105 = *(_QWORD *)(v55 + 144LL * v57 + 16);
      }
LABEL_93:
      v59 = *((_DWORD *)this + 6);
      v60 = 0;
      if ( v59 )
      {
        while ( 1 )
        {
          v61 = *(const wchar_t **)(v55 + 144LL * v60);
          if ( v61 )
          {
            if ( !wcsncmp_0(v61, L"filterid", 0xFFu) )
              break;
          }
          if ( ++v60 >= v59 )
            goto LABEL_100;
        }
        if ( *(_DWORD *)(v55 + 144LL * v60 + 8) == 9 )
          v106 = *(_QWORD *)(v55 + 144LL * v60 + 16);
      }
    }
LABEL_100:
    v62 = *((_QWORD *)this + 18);
    if ( !v62
      || (*(int (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v62 + 32LL))(v62, L"rulegroupname", pv) < 0 )
    {
      goto LABEL_113;
    }
    if ( LODWORD(pv[1]) == 10 )
    {
      if ( v109[0] )
      {
        v63 = -1;
        do
          ++v63;
        while ( *((_WORD *)v109[0] + v63) );
        if ( v63 )
        {
          CoTaskMemFree(*((LPVOID *)this + 24));
          v64 = v109[0];
          *((LPVOID *)this + 24) = v109[0];
          v107 = v64;
          v109[0] = 0;
        }
      }
    }
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    if ( LODWORD(pv[1]) == 10 )
    {
      v65 = v109[0];
    }
    else
    {
      if ( LODWORD(pv[1]) != 14 )
      {
LABEL_113:
        v66 = pv;
        v119 = 0;
        v67 = &v102;
        v9 = 0;
        *(_OWORD *)p = 0;
        v68 = 2;
        v118 = 0;
        do
        {
          v66 += 16;
          v69 = *v67;
          v70 = v67[1];
          v67 += 8;
          *((_OWORD *)v66 - 8) = v69;
          v71 = *(v67 - 6);
          *((_OWORD *)v66 - 7) = v70;
          v72 = *(v67 - 5);
          *((_OWORD *)v66 - 6) = v71;
          v73 = *(v67 - 4);
          *((_OWORD *)v66 - 5) = v72;
          v74 = *(v67 - 3);
          *((_OWORD *)v66 - 4) = v73;
          v75 = *(v67 - 2);
          *((_OWORD *)v66 - 3) = v74;
          v76 = *(v67 - 1);
          *((_OWORD *)v66 - 2) = v75;
          *((_OWORD *)v66 - 1) = v76;
          --v68;
        }
        while ( v68 );
        v77 = v67[1];
        *(_OWORD *)v66 = *v67;
        v78 = v67[2];
        v79 = (void *)*((_QWORD *)v67 + 6);
        *((_OWORD *)v66 + 1) = v77;
        *((_OWORD *)v66 + 2) = v78;
        v66[6] = v79;
        v80 = FwDiagCollectData(pv);
        if ( !v80 )
        {
          v81 = 0;
          v80 = 0;
          v98 = 0;
          v82 = 0;
          v102 = 0;
          memset(v103, 0, 136);
          if ( p[0] )
          {
            v83 = (_QWORD *)*((_QWORD *)p[0] + 5);
            if ( v83 )
            {
              if ( *v83 == *(_QWORD *)WF_FILTER_PROVIDER_GUID && v83[1] == 0x623D0FAEB48F1EBELL )
              {
                v84 = 0;
                while ( !v81 )
                {
                  v80 = ((__int64 (__fastcall *)(LPVOID *, __int128 *, int *))FW_DIAGNOSERS[v84])(pv, &v102, &v98);
                  if ( v80 )
                    goto LABEL_128;
                  v84 = (unsigned int)(v84 + 1);
                  if ( (unsigned int)v84 >= 8 )
                  {
                    if ( !v98 )
                      goto LABEL_131;
                    break;
                  }
                  v81 = v98;
                }
                v85 = FwAlloc(152);
                v6 = (int *)v85;
                if ( v85 )
                {
                  v82 = 1;
                  *(_OWORD *)v85 = v102;
                  *(_OWORD *)(v85 + 16) = *(_OWORD *)v103;
                  *(_OWORD *)(v85 + 32) = *(_OWORD *)&v103[2];
                  *(_OWORD *)(v85 + 48) = *(_OWORD *)&v103[4];
                  *(_OWORD *)(v85 + 64) = *(_OWORD *)&v103[6];
                  *(_OWORD *)(v85 + 80) = *(_OWORD *)&v103[8];
                  *(_OWORD *)(v85 + 96) = *(_OWORD *)&v103[10];
                  *(_OWORD *)(v85 + 112) = *(_OWORD *)&v103[12];
                  *(_OWORD *)(v85 + 128) = *(_OWORD *)&v103[14];
                  *(_QWORD *)(v85 + 144) = v103[16];
                  goto LABEL_131;
                }
                v80 = 8;
LABEL_128:
                switch ( DWORD1(v102) )
                {
                  case 0:
                  case 1:
                  case 2:
                  case 4:
                  case 5:
                  case 7:
                    FwFree(v103[0]);
                    break;
                  default:
                    break;
                }
              }
            }
          }
LABEL_131:
          if ( !v80 && v82 )
          {
            FwpmFreeMemory0(p);
            p[0] = 0;
            FWFreeFirewallRules(v118);
            *(_QWORD *)&v118 = 0;
            FWFreeFirewallRules(*((_QWORD *)&v118 + 1));
            v20 = v99;
            v86 = 0;
            *v99 = DS_CONFIRMED;
            *((_QWORD *)this + 20) = v6;
            *((_DWORD *)this + 42) = v82;
            v87 = *v6;
            if ( dword_1800158A0 == *v6
              || (v86 = 1, dword_1800158B4 == v87)
              || (v86 = 2, dword_1800158C8 == v87)
              || (v86 = 3, dword_1800158DC == v87)
              || (v86 = 4, dword_1800158F0 == v87)
              || (v86 = 5, dword_180015904 == v87) )
            {
              *((_OWORD *)this + 8) = *(__int128 *)((char *)&xmmword_180015890 + 20 * v86);
            }
            else
            {
              *((GUID *)this + 8) = GUID_NULL;
            }
            goto LABEL_148;
          }
        }
        FwpmFreeMemory0(p);
        p[0] = 0;
        FWFreeFirewallRules(v118);
        *(_QWORD *)&v118 = 0;
        FWFreeFirewallRules(*((_QWORD *)&v118 + 1));
        if ( !v80 )
          goto LABEL_147;
        if ( v80 > 0 )
          v9 = (unsigned __int16)v80 | 0x80070000;
        else
          v9 = v80;
        CWfHelperClass::WriteToNdfEtw(this, 2, L"Failed to Diagnose. Error Code [0x%x]", v9);
LABEL_146:
        if ( (v9 & 0x80000000) != 0 )
          return v9;
LABEL_147:
        v20 = v99;
        goto LABEL_148;
      }
      v65 = v109[1];
    }
    CoTaskMemFree(v65);
    goto LABEL_113;
  }
  *a5 = DS_PASSTHROUGH;
  *((_DWORD *)this + 44) = 1;
  v16 = *((_QWORD *)this + 18);
  if ( !v16 )
    goto LABEL_157;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPVOID *, int *))(*(_QWORD *)v16 + 32LL))(
         v16,
         L"serviceid",
         pv,
         a4) >= 0 )
  {
    if ( LODWORD(pv[1]) == 10 )
    {
      v17 = *((_QWORD *)this + 18);
      *(_QWORD *)&v102 = L"rulegroupname";
      *((_QWORD *)&v102 + 1) = 10;
      v103[0] = v109[0];
      memset(&v103[1], 0, 120);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 24LL))(v17, &v102);
    }
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    if ( LODWORD(pv[1]) == 10 )
    {
      CoTaskMemFree(v109[0]);
      v109[0] = 0;
    }
    else if ( LODWORD(pv[1]) == 14 )
    {
      CoTaskMemFree(v109[1]);
      v109[1] = 0;
    }
    LODWORD(pv[1]) = 0;
  }
  v18 = *((_QWORD *)this + 18);
  *((_QWORD *)&v102 + 1) = 1;
  *(_QWORD *)&v102 = L"HasReproRootCauseFound";
  memset(v103, 0, 128);
  result = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 40LL))(v18, &v102);
  v9 = result;
  if ( (int)result >= 0 )
  {
    CWfHelperClass::WriteToNdfEtw(this, 2, L"Set HasReproRootCauseFound to FALSE");
    goto LABEL_38;
  }
  return result;
}

```

## disassembly

```asm
0x1800049d0  mov     [rsp-8+arg_8], rbx
0x1800049d5  push    rbp
0x1800049d6  push    rsi
0x1800049d7  push    rdi
0x1800049d8  push    r12
0x1800049da  push    r13
0x1800049dc  push    r14
0x1800049de  push    r15
0x1800049e0  lea     rbp, [rsp-200h]
0x1800049e8  sub     rsp, 300h
0x1800049ef  mov     rax, cs:__security_cookie
0x1800049f6  xor     rax, rsp
0x1800049f9  mov     [rbp+230h+var_40], rax
0x180004a00  mov     r13, [rbp+230h+arg_20]
0x180004a07  lea     rbx, cs:180000000h
0x180004a0e  mov     eax, [rcx+0B8h]
0x180004a14  xor     r12d, r12d
0x180004a17  mov     [r8], r12
0x180004a1a  mov     r11, r8
0x180004a1d  mov     [rsp+330h+var_2F0], r8
0x180004a22  mov     rdi, rcx
0x180004a25  mov     dword ptr [r13+0], 2
0x180004a2d  mov     [rsp+330h+var_2F8], r13
0x180004a32  cmp     [rcx+98h], r12d
0x180004a39  jz      loc_180004E38
0x180004a3f  mov     esi, r12d
0x180004a42  cmp     [rcx+0B4h], r12d
0x180004a49  jnz     loc_180004C78
0x180004a4f  cmp     [rcx+9Ch], r12d
0x180004a56  jz      loc_180004E38
0x180004a5c  test    al, 2
0x180004a5e  ja      loc_1800056D0
0x180004a64  xor     edx, edx; dwCoInit
0x180004a66  mov     [rsp+330h+var_2E8], r12
0x180004a6b  xor     ecx, ecx; pvReserved
0x180004a6d  mov     [rsp+330h+var_300], r12d
0x180004a72  mov     ebx, r12d
0x180004a75  call    cs:__imp_CoInitializeEx
0x180004a7b  mov     ecx, 80000000h
0x180004a80  mov     r15d, 1
0x180004a86  mov     r14d, eax
0x180004a89  add     eax, ecx
0x180004a8b  test    ecx, eax
0x180004a8d  jnz     short loc_180004A9D
0x180004a8f  cmp     r14d, 80010106h
0x180004a96  jz      short loc_180004A9D
0x180004a98  mov     r12d, r14d
0x180004a9b  jmp     short loc_180004AF0
0x180004a9d  lea     rax, [rsp+330h+var_2E8]
0x180004aa2  mov     r8d, r15d; dwClsContext
0x180004aa5  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180004aac  mov     [rsp+330h+ppv], rax; ppv
0x180004ab1  xor     edx, edx; pUnkOuter
0x180004ab3  lea     rcx, CLSID_NetworkListManager; rclsid
0x180004aba  call    cs:__imp_CoCreateInstance
0x180004ac0  mov     r12d, eax
0x180004ac3  test    eax, eax
0x180004ac5  js      short loc_180004AF0
0x180004ac7  mov     rcx, [rsp+330h+var_2E8]
0x180004acc  lea     rdx, [rsp+330h+var_300]
0x180004ad1  mov     rax, [rcx]
0x180004ad4  mov     rax, [rax+68h]
0x180004ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004add  mov     r12d, eax
0x180004ae0  test    eax, eax
0x180004ae2  js      short loc_180004AF0
0x180004ae4  test    [rsp+330h+var_300], 770h
0x180004aec  cmova   ebx, r15d
0x180004af0  mov     rcx, [rsp+330h+var_2E8]
0x180004af5  test    rcx, rcx
0x180004af8  jz      short loc_180004B06
0x180004afa  mov     rax, [rcx]
0x180004afd  mov     rax, [rax+10h]
0x180004b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b06  test    r14d, r14d
0x180004b09  js      short loc_180004B11
0x180004b0b  call    cs:__imp_CoUninitialize
0x180004b11  test    r12d, r12d
0x180004b14  js      loc_180004E30
0x180004b1a  test    ebx, ebx
0x180004b1c  jz      loc_180004E30
0x180004b22  mov     rcx, [rdi+90h]
0x180004b29  lea     rbx, aHasreprorootca; "HasReproRootCauseFound"
0x180004b30  xorps   xmm0, xmm0
0x180004b33  lea     r8, [rbp+230h+pv]
0x180004b3a  movups  xmmword ptr [rbp+230h+pv], xmm0
0x180004b41  mov     rdx, rbx
0x180004b44  movups  xmmword ptr [rbp+230h+var_190], xmm0
0x180004b4b  movups  [rbp+230h+var_180], xmm0
0x180004b52  movups  [rbp+230h+var_170], xmm0
0x180004b59  movups  [rbp+230h+var_160], xmm0
0x180004b60  movups  [rbp+230h+var_150], xmm0
0x180004b67  movups  [rbp+230h+var_140], xmm0
0x180004b6e  movups  [rbp+230h+var_130], xmm0
0x180004b75  movups  [rbp+230h+var_120], xmm0
0x180004b7c  mov     rax, [rcx]
0x180004b7f  mov     rax, [rax+20h]
0x180004b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b88  test    eax, eax
0x180004b8a  js      short loc_180004BF4
0x180004b8c  mov     rcx, [rbp+230h+pv]; pv
0x180004b93  mov     r14d, dword ptr [rbp+230h+var_190]
0x180004b9a  call    cs:__imp_CoTaskMemFree
0x180004ba0  mov     eax, dword ptr [rbp+230h+pv+8]
0x180004ba6  xor     r12d, r12d
0x180004ba9  mov     [rbp+230h+pv], r12
0x180004bb0  cmp     eax, 0Ah
0x180004bb3  jz      short loc_180004BD0
0x180004bb5  cmp     eax, 0Eh
0x180004bb8  jnz     short loc_180004BE4
0x180004bba  mov     rcx, [rbp+230h+var_190+8]; pv
0x180004bc1  call    cs:__imp_CoTaskMemFree
0x180004bc7  mov     [rbp+230h+var_190+8], r12
0x180004bce  jmp     short loc_180004BE4
0x180004bd0  mov     rcx, [rbp+230h+var_190]; pv
0x180004bd7  call    cs:__imp_CoTaskMemFree
0x180004bdd  mov     [rbp+230h+var_190], r12
0x180004be4  mov     dword ptr [rbp+230h+pv+8], r12d
0x180004beb  test    r14d, r14d
0x180004bee  jnz     loc_180004E30
0x180004bf4  mov     rcx, [rdi+90h]
0x180004bfb  lea     rdx, [rsp+330h+var_2E0]
0x180004c00  xorps   xmm0, xmm0
0x180004c03  mov     qword ptr [rsp+330h+var_2E0+8], r15
0x180004c08  movups  [rbp+230h+var_26C], xmm0
0x180004c0c  mov     qword ptr [rsp+330h+var_2E0], rbx
0x180004c11  movups  [rsp+330h+var_2D0+4], xmm0
0x180004c16  mov     dword ptr [rsp+330h+var_2D0], r15d
0x180004c1b  movups  [rsp+330h+var_2BC], xmm0
0x180004c20  movups  [rbp+230h+var_2AC], xmm0
0x180004c24  movups  [rbp+230h+var_29C], xmm0
0x180004c28  movups  [rbp+230h+var_28C], xmm0
0x180004c2c  movups  [rbp+230h+var_27C], xmm0
0x180004c30  movups  [rbp+230h+var_26C+0Ch], xmm0
0x180004c34  mov     rax, [rcx]
0x180004c37  mov     rax, [rax+18h]
0x180004c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c40  mov     esi, eax
0x180004c42  test    eax, eax
0x180004c44  js      short loc_180004C5A
0x180004c46  lea     r8, aSetHasreproroo_0; "Set HasReproRootCauseFound to TRUE"
0x180004c4d  mov     edx, 2
0x180004c52  mov     rcx, rdi
0x180004c55  call    ?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)
0x180004c5a  movups  xmm0, cs:RCG_FW_NEEDS_REPRO
0x180004c61  mov     [rdi+0ACh], r15d
0x180004c68  movups  xmmword ptr [rdi+80h], xmm0
0x180004c6f  mov     [r13+0], r15d
0x180004c73  jmp     loc_18000564E
0x180004c78  mov     dword ptr [r13+0], 5
0x180004c80  mov     r15d, 1
0x180004c86  mov     [rcx+0B0h], r15d
0x180004c8d  mov     rcx, [rcx+90h]
0x180004c94  test    rcx, rcx
0x180004c97  jz      loc_1800056D0
0x180004c9d  xorps   xmm0, xmm0
0x180004ca0  lea     r8, [rbp+230h+pv]
0x180004ca7  movups  xmmword ptr [rbp+230h+pv], xmm0
0x180004cae  lea     rdx, aServiceid; "serviceid"
0x180004cb5  movups  xmmword ptr [rbp+230h+var_190], xmm0
0x180004cbc  movups  [rbp+230h+var_180], xmm0
0x180004cc3  movups  [rbp+230h+var_170], xmm0
0x180004cca  movups  [rbp+230h+var_160], xmm0
0x180004cd1  movups  [rbp+230h+var_150], xmm0
0x180004cd8  movups  [rbp+230h+var_140], xmm0
0x180004cdf  movups  [rbp+230h+var_130], xmm0
0x180004ce6  movups  [rbp+230h+var_120], xmm0
0x180004ced  mov     rax, [rcx]
0x180004cf0  mov     rax, [rax+20h]
0x180004cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf9  test    eax, eax
0x180004cfb  js      loc_180004DBF
0x180004d01  cmp     dword ptr [rbp+230h+pv+8], 0Ah
0x180004d08  jnz     short loc_180004D6A
0x180004d0a  mov     rcx, [rdi+90h]
0x180004d11  lea     rdx, aRulegroupname; "rulegroupname"
0x180004d18  xorps   xmm0, xmm0
0x180004d1b  mov     qword ptr [rsp+330h+var_2E0], rdx
0x180004d20  xor     eax, eax
0x180004d22  mov     qword ptr [rsp+330h+var_2E0+8], 0Ah
0x180004d2b  mov     qword ptr [rbp+230h+var_258], rax
0x180004d2f  lea     rdx, [rsp+330h+var_2E0]
0x180004d34  mov     rax, [rbp+230h+var_190]
0x180004d3b  mov     qword ptr [rsp+330h+var_2D0], rax
0x180004d40  movups  xmmword ptr [rsp+68h], xmm0
0x180004d45  movups  [rsp+330h+var_2BC+4], xmm0
0x180004d4a  movups  [rbp+230h+var_2AC+4], xmm0
0x180004d4e  movups  [rbp+230h+var_29C+4], xmm0
0x180004d52  movups  [rbp+230h+var_28C+4], xmm0
0x180004d56  movups  [rbp+230h+var_27C+4], xmm0
0x180004d5a  movups  [rbp+230h+var_26C+4], xmm0
0x180004d5e  mov     rax, [rcx]
0x180004d61  mov     rax, [rax+18h]
0x180004d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d6a  mov     rcx, [rbp+230h+pv]; pv
0x180004d71  call    cs:__imp_CoTaskMemFree
0x180004d77  mov     eax, dword ptr [rbp+230h+pv+8]
0x180004d7d  mov     [rbp+230h+pv], r12
0x180004d84  cmp     eax, 0Ah
0x180004d87  jz      short loc_180004DA4
0x180004d89  cmp     eax, 0Eh
0x180004d8c  jnz     short loc_180004DB8
0x180004d8e  mov     rcx, [rbp+230h+var_190+8]; pv
0x180004d95  call    cs:__imp_CoTaskMemFree
0x180004d9b  mov     [rbp+230h+var_190+8], r12
0x180004da2  jmp     short loc_180004DB8
0x180004da4  mov     rcx, [rbp+230h+var_190]; pv
0x180004dab  call    cs:__imp_CoTaskMemFree
0x180004db1  mov     [rbp+230h+var_190], r12
0x180004db8  mov     dword ptr [rbp+230h+pv+8], r12d
0x180004dbf  mov     rcx, [rdi+90h]
0x180004dc6  lea     rbx, aHasreprorootca; "HasReproRootCauseFound"
0x180004dcd  xorps   xmm0, xmm0
0x180004dd0  mov     qword ptr [rsp+330h+var_2E0+8], r15
0x180004dd5  movups  [rbp+230h+var_26C], xmm0
0x180004dd9  mov     qword ptr [rsp+330h+var_2E0], rbx
0x180004dde  lea     rdx, [rsp+330h+var_2E0]
0x180004de3  movups  [rsp+330h+var_2D0+4], xmm0
0x180004de8  mov     dword ptr [rsp+330h+var_2D0], r12d
0x180004ded  movups  [rsp+330h+var_2BC], xmm0
0x180004df2  movups  [rbp+230h+var_2AC], xmm0
0x180004df6  movups  [rbp+230h+var_29C], xmm0
0x180004dfa  movups  [rbp+230h+var_28C], xmm0
0x180004dfe  movups  [rbp+230h+var_27C], xmm0
0x180004e02  movups  [rbp+230h+var_26C+0Ch], xmm0
0x180004e06  mov     rax, [rcx]
0x180004e09  mov     rax, [rax+28h]
0x180004e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e12  mov     esi, eax
0x180004e14  test    eax, eax
0x180004e16  js      loc_180005751
0x180004e1c  lea     r8, aSetHasreproroo; "Set HasReproRootCauseFound to FALSE"
0x180004e23  mov     edx, 2
0x180004e28  mov     rcx, rdi
0x180004e2b  call    ?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ; CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)
0x180004e30  mov     rdx, r13
0x180004e33  jmp     loc_18000565B
0x180004e38  xorps   xmm0, xmm0
0x180004e3b  lea     rcx, [rsp+330h+var_2E0]; void *
0x180004e40  xor     edx, edx; Val
0x180004e42  mov     r8d, 138h; Size
0x180004e48  movups  xmmword ptr [rbp+230h+pv], xmm0
0x180004e4f  movups  xmmword ptr [rbp+230h+var_190], xmm0
0x180004e56  movups  [rbp+230h+var_180], xmm0
0x180004e5d  movups  [rbp+230h+var_170], xmm0
0x180004e64  movups  [rbp+230h+var_160], xmm0
0x180004e6b  movups  [rbp+230h+var_150], xmm0
0x180004e72  movups  [rbp+230h+var_140], xmm0
0x180004e79  movups  [rbp+230h+var_130], xmm0
0x180004e80  movups  [rbp+230h+var_120], xmm0
0x180004e87  call    memset_0
0x180004e8c  mov     rsi, [rdi+20h]
0x180004e90  test    rsi, rsi
0x180004e93  jz      loc_18000515D
0x180004e99  mov     r15d, [rdi+18h]
0x180004e9d  mov     ebx, r12d
0x180004ea0  test    r15d, r15d
0x180004ea3  jz      short loc_180004EF6
0x180004ea5  nop     word ptr [rax+rax+00000000h]
0x180004eb0  mov     eax, ebx
0x180004eb2  lea     r14, [rax+rax*8]
0x180004eb6  add     r14, r14
0x180004eb9  mov     rcx, [rsi+r14*8]; String1
0x180004ebd  test    rcx, rcx
0x180004ec0  jz      short loc_180004ED8
0x180004ec2  mov     r8d, 0FFh; MaxCount
0x180004ec8  lea     rdx, aProviderguid; "providerguid"
0x180004ecf  call    wcsncmp_0
0x180004ed4  test    eax, eax
0x180004ed6  jz      short loc_180004EE1
0x180004ed8  inc     ebx
0x180004eda  cmp     ebx, r15d
0x180004edd  jb      short loc_180004EB0
0x180004edf  jmp     short loc_180004EF6
0x180004ee1  cmp     dword ptr [rsi+r14*8+8], 0Bh
0x180004ee7  jnz     short loc_180004EF6
0x180004ee9  lea     rax, [rsi+10h]
0x180004eed  lea     rax, [rax+r14*8]
0x180004ef1  mov     qword ptr [rsp+330h+var_2E0], rax
0x180004ef6  mov     ebx, r12d
0x180004ef9  test    r15d, r15d
0x180004efc  jz      short loc_180004F43
0x180004efe  xchg    ax, ax
0x180004f00  mov     eax, ebx
0x180004f02  lea     r14, [rax+rax*8]
0x180004f06  add     r14, r14
0x180004f09  mov     rcx, [rsi+r14*8]; String1
0x180004f0d  test    rcx, rcx
0x180004f10  jz      short loc_180004F28
0x180004f12  mov     r8d, 0FFh; MaxCount
0x180004f18  lea     rdx, aTimestamp; "timestamp"
0x180004f1f  call    wcsncmp_0
0x180004f24  test    eax, eax
0x180004f26  jz      short loc_180004F31
0x180004f28  inc     ebx
0x180004f2a  cmp     ebx, r15d
0x180004f2d  jb      short loc_180004F00
0x180004f2f  jmp     short loc_180004F43
0x180004f31  cmp     dword ptr [rsi+r14*8+10h], 8
0x180004f37  jnz     short loc_180004F43
  ... truncated ...
```

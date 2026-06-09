# ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(Shield_ForceFieldProviderInfo *,Shield_ForceFieldProviderInfo * *)

- ea: `0x1800bebd8`
- end: `0x1800bedb2`
- name: `?DuplicateForceFieldProviderInfoEx@ForceFieldShield@ShieldProvider@@CAJPEAUShield_ForceFieldProviderInfo@@PEAPEAU3@@Z`
- size: `474`
- prototype: `__int64 __fastcall(struct Shield_ForceFieldProviderInfo *, struct Shield_ForceFieldProviderInfo **)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bf6a0`
- `0x1800bfab8`
- `0x1800bfd74`
- `0x1800c0f94`
- `0x1800c18cc`

## callees

- `0x18000d7fc`
- `0x1800be3f8`
- `0x1800bebd8`
- `0x1800e1764`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800bec40`
- `ole32!CoTaskMemFree` at `0x1800bec4a`
- `ole32!CoTaskMemFree` at `0x1800bec54`
- `ole32!CoTaskMemFree` at `0x1800bec5d`
- `ole32!CoTaskMemFree` at `0x1800bed7c`
- `ole32!CoTaskMemFree` at `0x1800bed86`
- `ole32!CoTaskMemFree` at `0x1800bed90`
- `ole32!CoTaskMemFree` at `0x1800bed99`
- `ole32!CoTaskMemFree` at `0x1800bec40`
- `ole32!CoTaskMemFree` at `0x1800bec4a`
- `ole32!CoTaskMemFree` at `0x1800bec54`
- `ole32!CoTaskMemFree` at `0x1800bec5d`
- `ole32!CoTaskMemFree` at `0x1800bed7c`
- `ole32!CoTaskMemFree` at `0x1800bed86`
- `ole32!CoTaskMemFree` at `0x1800bed90`
- `ole32!CoTaskMemFree` at `0x1800bed99`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ForceFieldShield::DuplicateForceFieldProviderInfoEx(
        struct Shield_ForceFieldProviderInfo *a1,
        struct Shield_ForceFieldProviderInfo **a2)
{
  int v4; // eax
  unsigned __int16 *v5; // r8
  int v6; // esi
  char *v7; // rbx
  unsigned __int16 **v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 **v12; // rdx
  unsigned __int16 **v13; // rdx
  int v14; // eax
  unsigned int v15; // edi
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  v4 = CommonUtil::UtilCoTaskMemAllocObject<Shield_ForceFieldProviderInfo>(&pv);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
        (unsigned int)v4);
    v7 = (char *)pv;
    goto LABEL_6;
  }
  v7 = (char *)pv;
  *(_OWORD *)pv = *(_OWORD *)a1;
  *((_DWORD *)v7 + 14) = *((_DWORD *)a1 + 14);
  *((_DWORD *)v7 + 10) = *((_DWORD *)a1 + 10);
  *((_DWORD *)v7 + 11) = *((_DWORD *)a1 + 11);
  *((_DWORD *)v7 + 12) = *((_DWORD *)a1 + 12);
  *((_DWORD *)v7 + 13) = *((_DWORD *)a1 + 13);
  v9 = (unsigned __int16 **)*((_QWORD *)a1 + 2);
  if ( v9 )
  {
    v6 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 16), v9, v5);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 76;
LABEL_14:
        WPP_SF_d(v10[2], v11, WPP_3533d4a562073f930570ad4a944aa956_Traceguids, (unsigned int)v6);
        goto LABEL_6;
      }
      goto LABEL_6;
    }
  }
  v12 = (unsigned __int16 **)*((_QWORD *)a1 + 3);
  if ( v12 )
  {
    v6 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 24), v12, v5);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 77;
        goto LABEL_14;
      }
LABEL_6:
      if ( v7 )
      {
        CoTaskMemFree(*((LPVOID *)v7 + 2));
        CoTaskMemFree(*((LPVOID *)v7 + 3));
        CoTaskMemFree(*((LPVOID *)v7 + 4));
        CoTaskMemFree(v7);
      }
      return (unsigned int)v6;
    }
  }
  v13 = (unsigned __int16 **)*((_QWORD *)a1 + 4);
  if ( v13 && (v14 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 32), v13, v5), v15 = v14, v14 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        WPP_3533d4a562073f930570ad4a944aa956_Traceguids,
        (unsigned int)v14);
    if ( v7 )
    {
      CoTaskMemFree(*((LPVOID *)v7 + 2));
      CoTaskMemFree(*((LPVOID *)v7 + 3));
      CoTaskMemFree(*((LPVOID *)v7 + 4));
      CoTaskMemFree(v7);
    }
    return v15;
  }
  else
  {
    *a2 = (struct Shield_ForceFieldProviderInfo *)v7;
    return 0;
  }
}

```

## disassembly

```asm
0x1800bebd8  push    rbx
0x1800bebda  push    rsi
0x1800bebdb  push    rdi
0x1800bebdc  push    r14
0x1800bebde  sub     rsp, 28h
0x1800bebe2  mov     rdi, rcx
0x1800bebe5  mov     [rsp+48h+pv], 0
0x1800bebee  lea     rcx, [rsp+48h+pv]
0x1800bebf3  mov     r14, rdx
0x1800bebf6  call    ??$UtilCoTaskMemAllocObject@UShield_ForceFieldProviderInfo@@@CommonUtil@@YAJPEAPEAUShield_ForceFieldProviderInfo@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<Shield_ForceFieldProviderInfo>(Shield_ForceFieldProviderInfo * *,unsigned __int64,bool)
0x1800bebfb  mov     esi, eax
0x1800bebfd  test    eax, eax
0x1800bebff  jns     short loc_1800BEC6A
0x1800bec01  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bec08  lea     rdx, WPP_GLOBAL_Control
0x1800bec0f  cmp     rcx, rdx
0x1800bec12  jz      short loc_1800BEC32
0x1800bec14  test    byte ptr [rcx+1Ch], 1
0x1800bec18  jz      short loc_1800BEC32
0x1800bec1a  mov     rcx, [rcx+10h]
0x1800bec1e  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800bec25  mov     edx, 4Bh ; 'K'
0x1800bec2a  mov     r9d, eax
0x1800bec2d  call    WPP_SF_d
0x1800bec32  mov     rbx, [rsp+48h+pv]
0x1800bec37  test    rbx, rbx
0x1800bec3a  jz      short loc_1800BEC63
0x1800bec3c  mov     rcx, [rbx+10h]; pv
0x1800bec40  call    cs:__imp_CoTaskMemFree
0x1800bec46  mov     rcx, [rbx+18h]; pv
0x1800bec4a  call    cs:__imp_CoTaskMemFree
0x1800bec50  mov     rcx, [rbx+20h]; pv
0x1800bec54  call    cs:__imp_CoTaskMemFree
0x1800bec5a  mov     rcx, rbx; pv
0x1800bec5d  call    cs:__imp_CoTaskMemFree
0x1800bec63  mov     eax, esi
0x1800bec65  jmp     loc_1800BEDA8
0x1800bec6a  mov     rbx, [rsp+48h+pv]
0x1800bec6f  movups  xmm0, xmmword ptr [rdi]
0x1800bec72  movdqu  xmmword ptr [rbx], xmm0
0x1800bec76  mov     eax, [rdi+38h]
0x1800bec79  mov     [rbx+38h], eax
0x1800bec7c  mov     eax, [rdi+28h]
0x1800bec7f  mov     [rbx+28h], eax
0x1800bec82  mov     eax, [rdi+2Ch]
0x1800bec85  mov     [rbx+2Ch], eax
0x1800bec88  mov     eax, [rdi+30h]
0x1800bec8b  mov     [rbx+30h], eax
0x1800bec8e  mov     eax, [rdi+34h]
0x1800bec91  mov     [rbx+34h], eax
0x1800bec94  mov     rdx, [rdi+10h]; unsigned __int16 **
0x1800bec98  test    rdx, rdx
0x1800bec9b  jz      short loc_1800BECEA
0x1800bec9d  lea     rcx, [rbx+10h]; this
0x1800beca1  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800beca6  mov     esi, eax
0x1800beca8  test    eax, eax
0x1800becaa  jns     short loc_1800BECEA
0x1800becac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800becb3  lea     rdx, WPP_GLOBAL_Control
0x1800becba  cmp     rcx, rdx
0x1800becbd  jz      loc_1800BEC37
0x1800becc3  test    byte ptr [rcx+1Ch], 1
0x1800becc7  jz      loc_1800BEC37
0x1800beccd  mov     edx, 4Ch ; 'L'
0x1800becd2  mov     rcx, [rcx+10h]
0x1800becd6  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800becdd  mov     r9d, esi
0x1800bece0  call    WPP_SF_d
0x1800bece5  jmp     loc_1800BEC37
0x1800becea  mov     rdx, [rdi+18h]; unsigned __int16 **
0x1800becee  test    rdx, rdx
0x1800becf1  jz      short loc_1800BED2A
0x1800becf3  lea     rcx, [rbx+18h]; this
0x1800becf7  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800becfc  mov     esi, eax
0x1800becfe  test    eax, eax
0x1800bed00  jns     short loc_1800BED2A
0x1800bed02  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed09  lea     rdx, WPP_GLOBAL_Control
0x1800bed10  cmp     rcx, rdx
0x1800bed13  jz      loc_1800BEC37
0x1800bed19  test    byte ptr [rcx+1Ch], 1
0x1800bed1d  jz      loc_1800BEC37
0x1800bed23  mov     edx, 4Dh ; 'M'
0x1800bed28  jmp     short loc_1800BECD2
0x1800bed2a  mov     rdx, [rdi+20h]; unsigned __int16 **
0x1800bed2e  test    rdx, rdx
0x1800bed31  jz      short loc_1800BEDA3
0x1800bed33  lea     rcx, [rbx+20h]; this
0x1800bed37  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800bed3c  mov     edi, eax
0x1800bed3e  test    eax, eax
0x1800bed40  jns     short loc_1800BEDA3
0x1800bed42  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bed49  lea     rdx, WPP_GLOBAL_Control
0x1800bed50  cmp     rcx, rdx
0x1800bed53  jz      short loc_1800BED73
0x1800bed55  test    byte ptr [rcx+1Ch], 1
0x1800bed59  jz      short loc_1800BED73
0x1800bed5b  mov     rcx, [rcx+10h]
0x1800bed5f  lea     r8, WPP_3533d4a562073f930570ad4a944aa956_Traceguids
0x1800bed66  mov     edx, 4Eh ; 'N'
0x1800bed6b  mov     r9d, eax
0x1800bed6e  call    WPP_SF_d
0x1800bed73  test    rbx, rbx
0x1800bed76  jz      short loc_1800BED9F
0x1800bed78  mov     rcx, [rbx+10h]; pv
0x1800bed7c  call    cs:__imp_CoTaskMemFree
0x1800bed82  mov     rcx, [rbx+18h]; pv
0x1800bed86  call    cs:__imp_CoTaskMemFree
0x1800bed8c  mov     rcx, [rbx+20h]; pv
0x1800bed90  call    cs:__imp_CoTaskMemFree
0x1800bed96  mov     rcx, rbx; pv
0x1800bed99  call    cs:__imp_CoTaskMemFree
0x1800bed9f  mov     eax, edi
0x1800beda1  jmp     short loc_1800BEDA8
0x1800beda3  mov     [r14], rbx
0x1800beda6  xor     eax, eax
0x1800beda8  add     rsp, 28h
0x1800bedac  pop     r14
0x1800bedae  pop     rdi
0x1800bedaf  pop     rsi
0x1800bedb0  pop     rbx
0x1800bedb1  retn
```

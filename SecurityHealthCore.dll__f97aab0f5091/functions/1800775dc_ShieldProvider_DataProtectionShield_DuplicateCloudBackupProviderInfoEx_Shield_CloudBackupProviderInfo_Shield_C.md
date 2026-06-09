# ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(Shield_CloudBackupProviderInfo *,Shield_CloudBackupProviderInfo * *)

- ea: `0x1800775dc`
- end: `0x180077862`
- name: `?DuplicateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUShield_CloudBackupProviderInfo@@PEAPEAU3@@Z`
- size: `646`
- prototype: `__int64 __fastcall(struct Shield_CloudBackupProviderInfo *, struct Shield_CloudBackupProviderInfo **)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180078190`
- `0x180078840`
- `0x180078ddc`
- `0x180079ef0`
- `0x18007afdc`

## callees

- `0x18000d7fc`
- `0x180076714`
- `0x1800775dc`
- `0x1800e1764`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180077644`
- `ole32!CoTaskMemFree` at `0x18007764e`
- `ole32!CoTaskMemFree` at `0x180077658`
- `ole32!CoTaskMemFree` at `0x180077662`
- `ole32!CoTaskMemFree` at `0x18007766c`
- `ole32!CoTaskMemFree` at `0x180077675`
- `ole32!CoTaskMemFree` at `0x180077818`
- `ole32!CoTaskMemFree` at `0x180077822`
- `ole32!CoTaskMemFree` at `0x18007782c`
- `ole32!CoTaskMemFree` at `0x180077836`
- `ole32!CoTaskMemFree` at `0x180077840`
- `ole32!CoTaskMemFree` at `0x180077849`
- `ole32!CoTaskMemFree` at `0x180077644`
- `ole32!CoTaskMemFree` at `0x18007764e`
- `ole32!CoTaskMemFree` at `0x180077658`
- `ole32!CoTaskMemFree` at `0x180077662`
- `ole32!CoTaskMemFree` at `0x18007766c`
- `ole32!CoTaskMemFree` at `0x180077675`
- `ole32!CoTaskMemFree` at `0x180077818`
- `ole32!CoTaskMemFree` at `0x180077822`
- `ole32!CoTaskMemFree` at `0x18007782c`
- `ole32!CoTaskMemFree` at `0x180077836`
- `ole32!CoTaskMemFree` at `0x180077840`
- `ole32!CoTaskMemFree` at `0x180077849`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfoEx(
        struct Shield_CloudBackupProviderInfo *a1,
        LPVOID **a2)
{
  int v4; // eax
  unsigned __int16 *v5; // r8
  int v6; // esi
  LPVOID *v7; // rbx
  unsigned __int16 **v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 **v12; // rdx
  unsigned __int16 **v13; // rdx
  unsigned __int16 **v14; // rdx
  unsigned __int16 **v15; // rdx
  int v16; // eax
  unsigned int v17; // edi
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  v4 = CommonUtil::UtilCoTaskMemAllocObject<Shield_CloudBackupProviderInfo>(&pv);
  v6 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        93,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v4);
    v7 = (LPVOID *)pv;
    goto LABEL_6;
  }
  v7 = (LPVOID *)pv;
  *(_OWORD *)((char *)pv + 4) = *(_OWORD *)((char *)a1 + 4);
  *(_DWORD *)v7 = *(_DWORD *)a1;
  *((_DWORD *)v7 + 16) = *((_DWORD *)a1 + 16);
  *((_DWORD *)v7 + 17) = *((_DWORD *)a1 + 17);
  *((_DWORD *)v7 + 18) = *((_DWORD *)a1 + 18);
  v9 = (unsigned __int16 **)*((_QWORD *)a1 + 3);
  if ( v9 )
  {
    v6 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 3), v9, v5);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 94;
LABEL_14:
        WPP_SF_d(v10[2], v11, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, (unsigned int)v6);
        goto LABEL_6;
      }
      goto LABEL_6;
    }
  }
  v12 = (unsigned __int16 **)*((_QWORD *)a1 + 4);
  if ( v12 )
  {
    v6 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 4), v12, v5);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 95;
        goto LABEL_14;
      }
LABEL_6:
      if ( v7 )
      {
        CoTaskMemFree(v7[3]);
        CoTaskMemFree(v7[4]);
        CoTaskMemFree(v7[5]);
        CoTaskMemFree(v7[6]);
        CoTaskMemFree(v7[7]);
        CoTaskMemFree(v7);
      }
      return (unsigned int)v6;
    }
  }
  v13 = (unsigned __int16 **)*((_QWORD *)a1 + 5);
  if ( v13 )
  {
    v6 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 5), v13, v5);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 96;
        goto LABEL_14;
      }
      goto LABEL_6;
    }
  }
  v14 = (unsigned __int16 **)*((_QWORD *)a1 + 6);
  if ( v14 )
  {
    v6 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 6), v14, v5);
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 97;
        goto LABEL_14;
      }
      goto LABEL_6;
    }
  }
  v15 = (unsigned __int16 **)*((_QWORD *)a1 + 7);
  if ( v15 && (v16 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v7 + 7), v15, v5), v17 = v16, v16 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v16);
    if ( v7 )
    {
      CoTaskMemFree(v7[3]);
      CoTaskMemFree(v7[4]);
      CoTaskMemFree(v7[5]);
      CoTaskMemFree(v7[6]);
      CoTaskMemFree(v7[7]);
      CoTaskMemFree(v7);
    }
    return v17;
  }
  else
  {
    *a2 = v7;
    return 0;
  }
}

```

## disassembly

```asm
0x1800775dc  push    rbx
0x1800775de  push    rsi
0x1800775df  push    rdi
0x1800775e0  push    r14
0x1800775e2  sub     rsp, 28h
0x1800775e6  mov     rdi, rcx
0x1800775e9  mov     [rsp+48h+pv], 0
0x1800775f2  lea     rcx, [rsp+48h+pv]
0x1800775f7  mov     r14, rdx
0x1800775fa  call    ??$UtilCoTaskMemAllocObject@UShield_CloudBackupProviderInfo@@@CommonUtil@@YAJPEAPEAUShield_CloudBackupProviderInfo@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<Shield_CloudBackupProviderInfo>(Shield_CloudBackupProviderInfo * *,unsigned __int64,bool)
0x1800775ff  mov     esi, eax
0x180077601  test    eax, eax
0x180077603  jns     short loc_180077682
0x180077605  mov     rcx, cs:WPP_GLOBAL_Control
0x18007760c  lea     rdx, WPP_GLOBAL_Control
0x180077613  cmp     rcx, rdx
0x180077616  jz      short loc_180077636
0x180077618  test    byte ptr [rcx+1Ch], 1
0x18007761c  jz      short loc_180077636
0x18007761e  mov     rcx, [rcx+10h]
0x180077622  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180077629  mov     edx, 5Dh ; ']'
0x18007762e  mov     r9d, eax
0x180077631  call    WPP_SF_d
0x180077636  mov     rbx, [rsp+48h+pv]
0x18007763b  test    rbx, rbx
0x18007763e  jz      short loc_18007767B
0x180077640  mov     rcx, [rbx+18h]; pv
0x180077644  call    cs:__imp_CoTaskMemFree
0x18007764a  mov     rcx, [rbx+20h]; pv
0x18007764e  call    cs:__imp_CoTaskMemFree
0x180077654  mov     rcx, [rbx+28h]; pv
0x180077658  call    cs:__imp_CoTaskMemFree
0x18007765e  mov     rcx, [rbx+30h]; pv
0x180077662  call    cs:__imp_CoTaskMemFree
0x180077668  mov     rcx, [rbx+38h]; pv
0x18007766c  call    cs:__imp_CoTaskMemFree
0x180077672  mov     rcx, rbx; pv
0x180077675  call    cs:__imp_CoTaskMemFree
0x18007767b  mov     eax, esi
0x18007767d  jmp     loc_180077858
0x180077682  mov     rbx, [rsp+48h+pv]
0x180077687  movups  xmm0, xmmword ptr [rdi+4]
0x18007768b  movdqu  xmmword ptr [rbx+4], xmm0
0x180077690  mov     eax, [rdi]
0x180077692  mov     [rbx], eax
0x180077694  mov     eax, [rdi+40h]
0x180077697  mov     [rbx+40h], eax
0x18007769a  mov     eax, [rdi+44h]
0x18007769d  mov     [rbx+44h], eax
0x1800776a0  mov     eax, [rdi+48h]
0x1800776a3  mov     [rbx+48h], eax
0x1800776a6  mov     rdx, [rdi+18h]; unsigned __int16 **
0x1800776aa  test    rdx, rdx
0x1800776ad  jz      short loc_1800776FC
0x1800776af  lea     rcx, [rbx+18h]; this
0x1800776b3  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800776b8  mov     esi, eax
0x1800776ba  test    eax, eax
0x1800776bc  jns     short loc_1800776FC
0x1800776be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800776c5  lea     rdx, WPP_GLOBAL_Control
0x1800776cc  cmp     rcx, rdx
0x1800776cf  jz      loc_18007763B
0x1800776d5  test    byte ptr [rcx+1Ch], 1
0x1800776d9  jz      loc_18007763B
0x1800776df  mov     edx, 5Eh ; '^'
0x1800776e4  mov     rcx, [rcx+10h]
0x1800776e8  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x1800776ef  mov     r9d, esi
0x1800776f2  call    WPP_SF_d
0x1800776f7  jmp     loc_18007763B
0x1800776fc  mov     rdx, [rdi+20h]; unsigned __int16 **
0x180077700  test    rdx, rdx
0x180077703  jz      short loc_18007773C
0x180077705  lea     rcx, [rbx+20h]; this
0x180077709  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007770e  mov     esi, eax
0x180077710  test    eax, eax
0x180077712  jns     short loc_18007773C
0x180077714  mov     rcx, cs:WPP_GLOBAL_Control
0x18007771b  lea     rdx, WPP_GLOBAL_Control
0x180077722  cmp     rcx, rdx
0x180077725  jz      loc_18007763B
0x18007772b  test    byte ptr [rcx+1Ch], 1
0x18007772f  jz      loc_18007763B
0x180077735  mov     edx, 5Fh ; '_'
0x18007773a  jmp     short loc_1800776E4
0x18007773c  mov     rdx, [rdi+28h]; unsigned __int16 **
0x180077740  test    rdx, rdx
0x180077743  jz      short loc_18007777F
0x180077745  lea     rcx, [rbx+28h]; this
0x180077749  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007774e  mov     esi, eax
0x180077750  test    eax, eax
0x180077752  jns     short loc_18007777F
0x180077754  mov     rcx, cs:WPP_GLOBAL_Control
0x18007775b  lea     rdx, WPP_GLOBAL_Control
0x180077762  cmp     rcx, rdx
0x180077765  jz      loc_18007763B
0x18007776b  test    byte ptr [rcx+1Ch], 1
0x18007776f  jz      loc_18007763B
0x180077775  mov     edx, 60h ; '`'
0x18007777a  jmp     loc_1800776E4
0x18007777f  mov     rdx, [rdi+30h]; unsigned __int16 **
0x180077783  test    rdx, rdx
0x180077786  jz      short loc_1800777C2
0x180077788  lea     rcx, [rbx+30h]; this
0x18007778c  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180077791  mov     esi, eax
0x180077793  test    eax, eax
0x180077795  jns     short loc_1800777C2
0x180077797  mov     rcx, cs:WPP_GLOBAL_Control
0x18007779e  lea     rdx, WPP_GLOBAL_Control
0x1800777a5  cmp     rcx, rdx
0x1800777a8  jz      loc_18007763B
0x1800777ae  test    byte ptr [rcx+1Ch], 1
0x1800777b2  jz      loc_18007763B
0x1800777b8  mov     edx, 61h ; 'a'
0x1800777bd  jmp     loc_1800776E4
0x1800777c2  mov     rdx, [rdi+38h]; unsigned __int16 **
0x1800777c6  test    rdx, rdx
0x1800777c9  jz      loc_180077853
0x1800777cf  lea     rcx, [rbx+38h]; this
0x1800777d3  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800777d8  mov     edi, eax
0x1800777da  test    eax, eax
0x1800777dc  jns     short loc_180077853
0x1800777de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800777e5  lea     rdx, WPP_GLOBAL_Control
0x1800777ec  cmp     rcx, rdx
0x1800777ef  jz      short loc_18007780F
0x1800777f1  test    byte ptr [rcx+1Ch], 1
0x1800777f5  jz      short loc_18007780F
0x1800777f7  mov     rcx, [rcx+10h]
0x1800777fb  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180077802  mov     edx, 62h ; 'b'
0x180077807  mov     r9d, eax
0x18007780a  call    WPP_SF_d
0x18007780f  test    rbx, rbx
0x180077812  jz      short loc_18007784F
0x180077814  mov     rcx, [rbx+18h]; pv
0x180077818  call    cs:__imp_CoTaskMemFree
0x18007781e  mov     rcx, [rbx+20h]; pv
0x180077822  call    cs:__imp_CoTaskMemFree
0x180077828  mov     rcx, [rbx+28h]; pv
0x18007782c  call    cs:__imp_CoTaskMemFree
0x180077832  mov     rcx, [rbx+30h]; pv
0x180077836  call    cs:__imp_CoTaskMemFree
0x18007783c  mov     rcx, [rbx+38h]; pv
0x180077840  call    cs:__imp_CoTaskMemFree
0x180077846  mov     rcx, rbx; pv
0x180077849  call    cs:__imp_CoTaskMemFree
0x18007784f  mov     eax, edi
0x180077851  jmp     short loc_180077858
0x180077853  mov     [r14], rbx
0x180077856  xor     eax, eax
0x180077858  add     rsp, 28h
0x18007785c  pop     r14
0x18007785e  pop     rdi
0x18007785f  pop     rsi
0x180077860  pop     rbx
0x180077861  retn
```

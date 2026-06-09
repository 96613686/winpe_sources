# ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfo(Shield_CloudBackupProviderInfo const *,Shield_CloudBackupProviderInfo *)

- ea: `0x1800774d4`
- end: `0x1800775d4`
- name: `?DuplicateCloudBackupProviderInfo@DataProtectionShield@ShieldProvider@@CAJPEBUShield_CloudBackupProviderInfo@@PEAU3@@Z`
- size: `256`
- prototype: `static int(const struct Shield_CloudBackupProviderInfo *, struct Shield_CloudBackupProviderInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180077870`

## callees

- `0x18000517c`
- `0x1800774d4`
- `0x1800e1764`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180077586`
- `ole32!CoTaskMemFree` at `0x180077590`
- `ole32!CoTaskMemFree` at `0x18007759a`
- `ole32!CoTaskMemFree` at `0x1800775a4`
- `ole32!CoTaskMemFree` at `0x1800775ae`
- `ole32!CoTaskMemFree` at `0x180077586`
- `ole32!CoTaskMemFree` at `0x180077590`
- `ole32!CoTaskMemFree` at `0x18007759a`
- `ole32!CoTaskMemFree` at `0x1800775a4`
- `ole32!CoTaskMemFree` at `0x1800775ae`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::DuplicateCloudBackupProviderInfo(
        const struct Shield_CloudBackupProviderInfo *a1,
        struct Shield_CloudBackupProviderInfo *a2,
        unsigned __int16 *a3)
{
  int v4; // edi
  unsigned __int16 **v6; // rdx
  unsigned __int16 **v7; // rdx
  unsigned __int16 **v8; // rdx
  unsigned __int16 **v9; // rdx
  unsigned __int16 **v10; // rdx

  v4 = 0;
  *(_OWORD *)((char *)a2 + 4) = *(_OWORD *)((char *)a1 + 4);
  *(_DWORD *)a2 = *(_DWORD *)a1;
  *((_DWORD *)a2 + 16) = *((_DWORD *)a1 + 16);
  *((_DWORD *)a2 + 17) = *((_DWORD *)a1 + 17);
  *((_DWORD *)a2 + 18) = *((_DWORD *)a1 + 18);
  v6 = (unsigned __int16 **)*((_QWORD *)a1 + 3);
  if ( v6 )
  {
    v4 = CommonUtil::UtilCoDuplicateString((struct Shield_CloudBackupProviderInfo *)((char *)a2 + 24), v6, a3);
    if ( v4 < 0 )
      goto LABEL_11;
  }
  v7 = (unsigned __int16 **)*((_QWORD *)a1 + 4);
  if ( v7 )
  {
    v4 = CommonUtil::UtilCoDuplicateString((struct Shield_CloudBackupProviderInfo *)((char *)a2 + 32), v7, a3);
    if ( v4 < 0 )
      goto LABEL_11;
  }
  if ( (v8 = (unsigned __int16 **)*((_QWORD *)a1 + 5)) != 0
    && (v4 = CommonUtil::UtilCoDuplicateString((struct Shield_CloudBackupProviderInfo *)((char *)a2 + 40), v8, a3),
        v4 < 0)
    || (v9 = (unsigned __int16 **)*((_QWORD *)a1 + 6)) != 0
    && (v4 = CommonUtil::UtilCoDuplicateString((struct Shield_CloudBackupProviderInfo *)((char *)a2 + 48), v9, a3),
        v4 < 0)
    || (v10 = (unsigned __int16 **)*((_QWORD *)a1 + 7)) != 0
    && (v4 = CommonUtil::UtilCoDuplicateString((struct Shield_CloudBackupProviderInfo *)((char *)a2 + 56), v10, a3),
        v4 < 0) )
  {
LABEL_11:
    CoTaskMemFree(*((LPVOID *)a2 + 3));
    CoTaskMemFree(*((LPVOID *)a2 + 4));
    CoTaskMemFree(*((LPVOID *)a2 + 5));
    CoTaskMemFree(*((LPVOID *)a2 + 6));
    CoTaskMemFree(*((LPVOID *)a2 + 7));
    memset_0(a2, 0, 0x50u);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800774d4  mov     [rsp+arg_0], rbx
0x1800774d9  mov     [rsp+arg_8], rsi
0x1800774de  push    rdi
0x1800774df  sub     rsp, 20h
0x1800774e3  movups  xmm0, xmmword ptr [rcx+4]
0x1800774e7  mov     rbx, rdx
0x1800774ea  xor     edi, edi
0x1800774ec  mov     rsi, rcx
0x1800774ef  movdqu  xmmword ptr [rdx+4], xmm0
0x1800774f4  mov     eax, [rcx]
0x1800774f6  mov     [rdx], eax
0x1800774f8  mov     eax, [rcx+40h]
0x1800774fb  mov     [rdx+40h], eax
0x1800774fe  mov     eax, [rcx+44h]
0x180077501  mov     [rdx+44h], eax
0x180077504  mov     eax, [rcx+48h]
0x180077507  mov     [rdx+48h], eax
0x18007750a  mov     rdx, [rcx+18h]; unsigned __int16 **
0x18007750e  test    rdx, rdx
0x180077511  jz      short loc_180077522
0x180077513  lea     rcx, [rbx+18h]; this
0x180077517  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007751c  mov     edi, eax
0x18007751e  test    eax, eax
0x180077520  js      short loc_180077582
0x180077522  mov     rdx, [rsi+20h]; unsigned __int16 **
0x180077526  test    rdx, rdx
0x180077529  jz      short loc_18007753A
0x18007752b  lea     rcx, [rbx+20h]; this
0x18007752f  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180077534  mov     edi, eax
0x180077536  test    eax, eax
0x180077538  js      short loc_180077582
0x18007753a  mov     rdx, [rsi+28h]; unsigned __int16 **
0x18007753e  test    rdx, rdx
0x180077541  jz      short loc_180077552
0x180077543  lea     rcx, [rbx+28h]; this
0x180077547  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007754c  mov     edi, eax
0x18007754e  test    eax, eax
0x180077550  js      short loc_180077582
0x180077552  mov     rdx, [rsi+30h]; unsigned __int16 **
0x180077556  test    rdx, rdx
0x180077559  jz      short loc_18007756A
0x18007755b  lea     rcx, [rbx+30h]; this
0x18007755f  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180077564  mov     edi, eax
0x180077566  test    eax, eax
0x180077568  js      short loc_180077582
0x18007756a  mov     rdx, [rsi+38h]; unsigned __int16 **
0x18007756e  test    rdx, rdx
0x180077571  jz      short loc_1800775C2
0x180077573  lea     rcx, [rbx+38h]; this
0x180077577  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007757c  mov     edi, eax
0x18007757e  test    eax, eax
0x180077580  jns     short loc_1800775C2
0x180077582  mov     rcx, [rbx+18h]; pv
0x180077586  call    cs:__imp_CoTaskMemFree
0x18007758c  mov     rcx, [rbx+20h]; pv
0x180077590  call    cs:__imp_CoTaskMemFree
0x180077596  mov     rcx, [rbx+28h]; pv
0x18007759a  call    cs:__imp_CoTaskMemFree
0x1800775a0  mov     rcx, [rbx+30h]; pv
0x1800775a4  call    cs:__imp_CoTaskMemFree
0x1800775aa  mov     rcx, [rbx+38h]; pv
0x1800775ae  call    cs:__imp_CoTaskMemFree
0x1800775b4  xor     edx, edx; Val
0x1800775b6  mov     rcx, rbx; void *
0x1800775b9  lea     r8d, [rdx+50h]; Size
0x1800775bd  call    memset_0
0x1800775c2  mov     rbx, [rsp+28h+arg_0]
0x1800775c7  mov     eax, edi
0x1800775c9  mov     rsi, [rsp+28h+arg_8]
0x1800775ce  add     rsp, 20h
0x1800775d2  pop     rdi
0x1800775d3  retn
```

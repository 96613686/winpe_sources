# ReadDeviceListSubMethod

- ea: `0x1800818cc`
- end: `0x1800832d9`
- name: `ReadDeviceListSubMethod`
- size: `6669`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180088bec`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bfb0`
- `0x18005cc20`
- `0x18007ffdc`
- `0x1800818cc`
- `0x1800884c4`
- `0x180088564`
- `0x180088d0c`
- `0x180088db4`
- `0x180089164`
- `0x180089624`
- `0x1800e7206`
- `0x1800e721e`
- `0x1800e7260`
- `0x1800e9010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081edd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081f31`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008222f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180082bdf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081edd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180081f31`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008222f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180082bdf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180081ecc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180081f1d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008225e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082284`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800822aa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800822d0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800822f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008231c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082342`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082364`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082386`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800823a8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180081ecc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180081f1d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008225e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082284`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800822aa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800822d0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800822f6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008231c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082342`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082364`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180082386`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800823a8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180081a6d`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180081c4b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180081e5b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008206f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800820a1`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180082103`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180082224`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180081a6d`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180081c4b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180081e5b`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18008206f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800820a1`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180082103`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180082224`

## string_xrefs

- `0x180081c05`: `EnableCompression`
- `0x180081d5f`: `Compression`
- `0x180081d3e`: `Protocol`
- `0x180081dbb`: `MdmProtocol`

## pseudocode

```c
__int64 __fastcall ReadDeviceListSubMethod(
        HKEY hkey,
        __int64 (__fastcall *a2)(char *),
        int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  __int64 v7; // r13
  __int64 (__fastcall *v8)(char *); // rbx
  int v11; // r12d
  DWORD v12; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // r9d
  unsigned int PhoneList; // eax
  unsigned int String; // ebx
  unsigned int Long; // eax
  unsigned int Flag; // eax
  unsigned int v20; // eax
  _DWORD *v21; // r12
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // edx
  int v27; // r8d
  int v28; // r9d
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  _DWORD *v36; // r8
  unsigned int v37; // eax
  unsigned int v38; // eax
  struct _LIST_ENTRY *v39; // rcx
  __int64 v40; // rdx
  WCHAR *v41; // rbx
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  _WORD *v46; // rax
  int v47; // edx
  int v48; // r8d
  int v49; // r9d
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  CHAR *v54; // r13
  __int64 v55; // rax
  const WCHAR *v56; // r12
  int v57; // ebx
  int v58; // edx
  int v59; // r8d
  int v60; // r9d
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  WCHAR *v65; // rcx
  struct _LIST_ENTRY *v66; // rcx
  __int64 v67; // rdx
  struct _LIST_ENTRY *v68; // rcx
  __int64 v69; // rdx
  int lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  int lpString2b; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+40h] [rbp-C0h] BYREF
  int v74; // [rsp+44h] [rbp-BCh]
  int v75; // [rsp+48h] [rbp-B8h]
  int v76; // [rsp+4Ch] [rbp-B4h]
  int v77; // [rsp+50h] [rbp-B0h]
  __int64 (__fastcall *v78)(char *); // [rsp+58h] [rbp-A8h]
  int v79; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  PCNZWCH v81; // [rsp+68h] [rbp-98h]
  DWORD i; // [rsp+70h] [rbp-90h]
  __int64 v83; // [rsp+78h] [rbp-88h]
  char Destination[1552]; // [rsp+80h] [rbp-80h] BYREF
  char Source[1552]; // [rsp+690h] [rbp+590h] BYREF

  v7 = a4;
  v83 = a4;
  v8 = a2;
  v76 = a3;
  v78 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 282, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids);
  }
  memset_0(Source, 0, 0x602u);
  cSubKeys = 0;
  if ( (unsigned int)RegGetNumberOfSubkeys(hkey, &cSubKeys) )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 283, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 1);
    }
    return 1;
  }
  v11 = 0;
  v74 = 0;
  v12 = 0;
  v77 = 0;
  v75 = 0;
  for ( i = 0; v12 < cSubKeys; i = v12 )
  {
    if ( !(unsigned int)RegGetIthSectionName(hkey, v12, Source) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 284, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids);
      }
      return 635;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 285, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, Source);
    }
    strncpy_0(Destination, Source, 0x601u);
    if ( CompareStringA(0x7Fu, 1u, "isdn", -1, Source, -1) == 2 )
    {
      *(_QWORD *)(a5 + 32) = v8(Source);
      lpString2 = v76;
      *(_DWORD *)(a5 + 40) = 6;
      PhoneList = RegReadPhoneList((_DWORD)hkey, v13, v14, v15, lpString2, a5 + 168, (__int64)Destination);
      String = PhoneList;
      if ( PhoneList )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 286, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, PhoneList);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 287;
            goto LABEL_180;
          }
        }
        return String;
      }
      Long = RegReadLong(hkey, "LastSelectedPhone");
      String = Long;
      if ( Long )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 288, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, Long);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 289;
            goto LABEL_180;
          }
        }
        return String;
      }
      Flag = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Destination);
      String = Flag;
      if ( Flag )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 290, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, Flag);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 291;
            goto LABEL_180;
          }
        }
        return String;
      }
      v20 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Destination);
      String = v20;
      if ( v20 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 292, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v20);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 293;
            goto LABEL_180;
          }
        }
        return String;
      }
      v21 = (_DWORD *)(a5 + 132);
      String = RegReadLong(hkey, "LineType");
      if ( String )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 294, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, String);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 295;
            goto LABEL_180;
          }
        }
        return String;
      }
      if ( *v21 > 2u )
        *v21 = 0;
      v22 = RegReadFlag(hkey, "Fallback", a5 + 136, Destination);
      String = v22;
      if ( v22 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 296, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v22);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 297;
            goto LABEL_180;
          }
        }
        return String;
      }
      *(_DWORD *)(a5 + 128) = 1;
      v23 = RegReadFlag(hkey, "Proprietary", a5 + 128, Destination);
      String = v23;
      if ( v23 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 298, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v23);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 299;
            goto LABEL_180;
          }
        }
        return String;
      }
      v73 = -1;
      v24 = RegReadLong(hkey, "ChannelAggregation");
      String = v24;
      if ( v24 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 300, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v24);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 301;
            goto LABEL_180;
          }
        }
        return String;
      }
      if ( v73 == -1 )
        *(_DWORD *)(a5 + 128) = 0;
      else
        *(_DWORD *)(a5 + 144) = v73;
      v25 = RegReadFlag(hkey, "EnableCompression", a5 + 140, Destination);
      String = v25;
      if ( v25 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 302, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v25);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 303;
            goto LABEL_180;
          }
        }
        return String;
      }
      goto LABEL_32;
    }
    if ( CompareStringA(0x7Fu, 1u, "modem", -1, Source, -1) == 2 )
    {
      *(_QWORD *)(a5 + 32) = v8(Source);
      lpString2a = v76;
      *(_DWORD *)(a5 + 40) = 3;
      v29 = RegReadPhoneList((_DWORD)hkey, v26, v27, v28, lpString2a, a5 + 168, (__int64)Destination);
      String = v29;
      if ( v29 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 304, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v29);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 305;
            goto LABEL_180;
          }
        }
        return String;
      }
      v30 = RegReadLong(hkey, "LastSelectedPhone");
      String = v30;
      if ( v30 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 306, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v30);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 307;
            goto LABEL_180;
          }
        }
        return String;
      }
      v31 = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Destination);
      String = v31;
      if ( v31 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 308, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v31);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 309;
            goto LABEL_180;
          }
        }
        return String;
      }
      v32 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Destination);
      String = v32;
      if ( v32 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 310, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v32);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 311;
            goto LABEL_180;
          }
        }
        return String;
      }
      v33 = RegReadFlag(hkey, "HwFlowControl", a5 + 108, Destination);
      String = v33;
      if ( v33 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 312, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v33);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 313;
            goto LABEL_180;
          }
        }
        return String;
      }
      v34 = RegReadFlag(hkey, "Protocol", a5 + 112, Destination);
      String = v34;
      if ( v34 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 314, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v34);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 315;
            goto LABEL_180;
          }
        }
        return String;
      }
      v35 = RegReadFlag(hkey, "Compression", a5 + 116, Destination);
      String = v35;
      if ( v35 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 316, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v35);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 317;
            goto LABEL_180;
          }
        }
        return String;
      }
      v36 = (_DWORD *)(a5 + 120);
      if ( a7 )
      {
        *v36 = *a7 == 0;
      }
      else
      {
        v37 = RegReadFlag(hkey, "Speaker", v36, Destination);
        String = v37;
        if ( v37 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 318, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v37);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 319;
              goto LABEL_180;
            }
          }
          return String;
        }
      }
      v38 = RegReadLong(hkey, "MdmProtocol");
      String = v38;
      if ( v38 )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 320, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v38);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 321;
            goto LABEL_180;
          }
        }
        return String;
      }
      v11 = 1;
      v77 = 1;
    }
    else if ( CompareStringA(0x7Fu, 1u, "switch", -1, Source, -1) == 2 )
    {
      v81 = 0;
      String = RegReadString(hkey, "Type");
      if ( String )
      {
        v39 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 322, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, String);
            v39 = WPP_GLOBAL_Control;
          }
          if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v39[1].Blink) < 0 && BYTE1(v39[1].Blink) >= 6u )
          {
            v40 = 323;
            goto LABEL_180;
          }
        }
        return String;
      }
      v41 = (WCHAR *)v81;
      if ( !v81 )
      {
        v79 = 0;
        v73 = 0;
        v81 = 0;
        v42 = RegReadFlag(hkey, "Terminal", &v79, Destination);
        String = v42;
        if ( v42 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 325, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v42);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 326;
              goto LABEL_180;
            }
          }
          return String;
        }
        v43 = RegReadFlag(hkey, "Script", &v73, Destination);
        String = v43;
        if ( v43 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 327, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v43);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 328;
              goto LABEL_180;
            }
          }
          return String;
        }
        v44 = RegReadLong(hkey, "CustomScript");
        String = v44;
        if ( v44 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 329, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v44);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 330;
              goto LABEL_180;
            }
          }
          return String;
        }
        v45 = RegReadString(hkey, "Name");
        String = v45;
        if ( v45 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 331, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v45);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 332;
              goto LABEL_180;
            }
          }
          return String;
        }
        if ( v74 || v11 )
        {
          if ( v75 )
          {
            *(_DWORD *)(v7 + 536) = 1;
            v66 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v67 = 333;
              goto LABEL_389;
            }
            return 0;
          }
          *(_DWORD *)(v7 + 212) = v79;
          *(_DWORD *)(v7 + 216) = v73;
          *(_QWORD *)(v7 + 224) = v81;
          v75 = 1;
        }
        else
        {
          *(_DWORD *)(a5 + 88) = v79;
          *(_DWORD *)(a5 + 92) = v73;
          *(_QWORD *)(a5 + 96) = v81;
          v74 = 1;
        }
        goto LABEL_86;
      }
      if ( v74 || v11 )
      {
        if ( v75 )
        {
          v65 = (WCHAR *)v81;
          *(_DWORD *)(v7 + 536) = 1;
          GlobalFree(v65);
          v66 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
          {
            v67 = 324;
            goto LABEL_389;
          }
          return 0;
        }
        if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, v81, -1) == 2 )
        {
          *(_DWORD *)(v7 + 212) = 1;
          GlobalFree(v41);
        }
        else
        {
          *(_DWORD *)(v7 + 216) = 1;
          *(_QWORD *)(v7 + 224) = v41;
        }
        v75 = 1;
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, L"Terminal", -1, v81, -1) == 2 )
        {
          *(_DWORD *)(a5 + 88) = 1;
          GlobalFree(v41);
        }
        else
        {
          *(_DWORD *)(a5 + 92) = 1;
          *(_QWORD *)(a5 + 96) = v41;
        }
        v74 = 1;
      }
    }
    else
    {
      if ( CompareStringA(0x7Fu, 1u, "pad", -1, Source, -1) == 2 )
        goto LABEL_47;
      if ( CompareStringA(0x7Fu, 1u, "null", -1, Source, -1) == 2 )
      {
        *(_QWORD *)(a5 + 32) = v8(Source);
        *(_DWORD *)(a5 + 40) = 1;
        goto LABEL_47;
      }
      v46 = *(_WORD **)(a5 + 16);
      if ( v46 && !*v46 && CompareStringA(0x7Fu, 1u, "ATM", -1, Source, -1) == 2 )
      {
        *(_QWORD *)(a5 + 32) = v8(Source);
        lpString2b = v76;
        *(_DWORD *)(a5 + 40) = 13;
        v50 = RegReadPhoneList((_DWORD)hkey, v47, v48, v49, lpString2b, a5 + 168, (__int64)Destination);
        String = v50;
        if ( v50 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 334, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v50);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 335;
              goto LABEL_180;
            }
          }
          return String;
        }
        v51 = RegReadLong(hkey, "LastSelectedPhone");
        String = v51;
        if ( v51 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 336, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v51);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 337;
              goto LABEL_180;
            }
          }
          return String;
        }
        v52 = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Destination);
        String = v52;
        if ( v52 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 338, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v52);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 339;
              goto LABEL_180;
            }
          }
          return String;
        }
        v53 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Destination);
        String = v53;
        if ( v53 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 340, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v53);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 341;
              goto LABEL_180;
            }
          }
          return String;
        }
        goto LABEL_86;
      }
      v54 = (CHAR *)StrDupAFromTInternal(*(LPCWCH *)(a5 + 24));
      if ( !v54 )
      {
        v68 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        {
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 342, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 8);
            v68 = WPP_GLOBAL_Control;
          }
          if ( v68 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v68[1].Blink) < 0 && BYTE1(v68[1].Blink) >= 6u )
          {
            v69 = 343;
LABEL_378:
            WPP_SF_d(v68[1].Flink, v69, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 8);
          }
        }
        return 8;
      }
      v55 = v8(Source);
      *(_QWORD *)(a5 + 32) = v55;
      v56 = (const WCHAR *)v55;
      if ( !v55 )
      {
        v68 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          v69 = 344;
          goto LABEL_378;
        }
        return 8;
      }
      v57 = CompareStringA(0x7Fu, 1u, Source, -1, v54, -1);
      GlobalFree(v54);
      if ( v57 == 2
        || CompareStringW(0x7Fu, 1u, L"SERIAL", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"vpn", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"GENERIC", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"FRAMERELAY", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"ATM", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"SONET", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"SW56", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"IRDA", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"PARALLEL", -1, v56, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"PPPoE", -1, v56, -1) == 2 )
      {
        if ( !*(_DWORD *)(a5 + 40) )
          *(_DWORD *)(a5 + 40) = PbdevicetypeFromPszTypeA(Source);
        v61 = RegReadPhoneList((_DWORD)hkey, v58, v59, v60, v76, a5 + 168, (__int64)Source);
        String = v61;
        if ( v61 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 345, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v61);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 346;
              goto LABEL_180;
            }
          }
          return String;
        }
        v62 = RegReadLong(hkey, "LastSelectedPhone");
        String = v62;
        if ( v62 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 347, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v62);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 348;
              goto LABEL_180;
            }
          }
          return String;
        }
        v63 = RegReadFlag(hkey, "PromoteAlternates", a5 + 180, Source);
        String = v63;
        if ( v63 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 349, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v63);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 350;
              goto LABEL_180;
            }
          }
          return String;
        }
        v64 = RegReadFlag(hkey, "TryNextAlternateOnFail", a5 + 184, Source);
        String = v64;
        if ( v64 )
        {
          v39 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 351, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v64);
              v39 = WPP_GLOBAL_Control;
            }
            if ( v39 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(v39[1].Blink) < 0
              && BYTE1(v39[1].Blink) >= 6u )
            {
              v40 = 352;
              goto LABEL_180;
            }
          }
          return String;
        }
        v7 = v83;
LABEL_32:
        v11 = v77;
LABEL_86:
        v8 = v78;
        goto LABEL_47;
      }
      v7 = v83;
      v11 = v77;
      *(_DWORD *)(v83 + 536) = 1;
    }
    v8 = v78;
LABEL_47:
    v12 = i + 1;
  }
  if ( *(_DWORD *)(a5 + 40) )
  {
    v66 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v67 = 354;
LABEL_389:
      WPP_SF_d(v66[1].Flink, v67, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, 0);
    }
    return 0;
  }
  else
  {
    v39 = WPP_GLOBAL_Control;
    String = 625;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      v40 = 353;
LABEL_180:
      WPP_SF_d(v39[1].Flink, v40, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, String);
    }
    return String;
  }
}

```

## disassembly

```asm
0x1800818cc  push    rbp
0x1800818ce  push    rbx
0x1800818cf  push    rsi
0x1800818d0  push    rdi
0x1800818d1  push    r12
0x1800818d3  push    r13
0x1800818d5  push    r14
0x1800818d7  push    r15
0x1800818d9  lea     rbp, [rsp-0BB8h]
0x1800818e1  sub     rsp, 0CB8h
0x1800818e8  mov     rax, cs:__security_cookie
0x1800818ef  xor     rax, rsp
0x1800818f2  mov     [rbp+0BF0h+var_50], rax
0x1800818f9  mov     r14, [rbp+0BF0h+arg_20]
0x180081900  mov     r13, r9
0x180081903  mov     [rsp+0CF0h+var_C78], r9
0x180081908  mov     rbx, rdx
0x18008190b  mov     [rsp+0CF0h+var_CA4], r8d
0x180081910  mov     r15, rcx
0x180081913  mov     [rsp+0CF0h+var_C98], rdx
0x180081918  mov     rcx, cs:WPP_GLOBAL_Control
0x18008191f  lea     rdi, WPP_GLOBAL_Control
0x180081926  cmp     rcx, rdi
0x180081929  jz      short loc_18008194C
0x18008192b  test    byte ptr [rcx+1Ch], 80h
0x18008192f  jz      short loc_18008194C
0x180081931  cmp     byte ptr [rcx+19h], 6
0x180081935  jb      short loc_18008194C
0x180081937  mov     rcx, [rcx+10h]
0x18008193b  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180081942  mov     edx, 11Ah
0x180081947  call    WPP_SF_
0x18008194c  xor     edx, edx; Val
0x18008194e  lea     rcx, [rbp+0BF0h+Source]; void *
0x180081955  mov     r8d, 602h; Size
0x18008195b  call    memset_0
0x180081960  lea     rdx, [rsp+0CF0h+cSubKeys]; lpcSubKeys
0x180081965  mov     [rsp+0CF0h+cSubKeys], 0
0x18008196d  mov     rcx, r15; hKey
0x180081970  call    RegGetNumberOfSubkeys
0x180081975  xor     ecx, ecx
0x180081977  test    eax, eax
0x180081979  jz      short loc_1800819B8
0x18008197b  lea     esi, [rcx+1]
0x18008197e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081985  cmp     rcx, rdi
0x180081988  jz      short loc_1800819B1
0x18008198a  test    byte ptr [rcx+1Ch], 80h
0x18008198e  jz      short loc_1800819B1
0x180081990  lea     edi, [rsi+1]
0x180081993  cmp     [rcx+19h], dil
0x180081997  jb      short loc_1800819B1
0x180081999  mov     rcx, [rcx+10h]
0x18008199d  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x1800819a4  mov     edx, 11Bh
0x1800819a9  mov     r9d, esi
0x1800819ac  call    WPP_SF_d
0x1800819b1  mov     eax, esi
0x1800819b3  jmp     loc_1800832B6
0x1800819b8  mov     r12d, ecx
0x1800819bb  mov     [rsp+0CF0h+var_CAC], ecx
0x1800819bf  mov     eax, ecx
0x1800819c1  mov     [rsp+0CF0h+var_CA0], ecx
0x1800819c5  mov     [rsp+0CF0h+var_CA8], ecx
0x1800819c9  mov     [rsp+0CF0h+var_C80], ecx
0x1800819cd  cmp     [rsp+0CF0h+cSubKeys], ecx
0x1800819d1  jbe     loc_180081DFA
0x1800819d7  mov     edi, 2
0x1800819dc  lea     esi, [rdi-1]
0x1800819df  lea     r8, [rbp+0BF0h+Source]
0x1800819e6  mov     edx, eax
0x1800819e8  mov     rcx, r15
0x1800819eb  call    RegGetIthSectionName
0x1800819f0  test    eax, eax
0x1800819f2  jz      loc_180083249
0x1800819f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800819ff  lea     rax, WPP_GLOBAL_Control
0x180081a06  cmp     rcx, rax
0x180081a09  jz      short loc_180081A33
0x180081a0b  test    byte ptr [rcx+1Ch], 80h
0x180081a0f  jz      short loc_180081A33
0x180081a11  cmp     byte ptr [rcx+19h], 5
0x180081a15  jb      short loc_180081A33
0x180081a17  mov     rcx, [rcx+10h]
0x180081a1b  lea     r9, [rbp+0BF0h+Source]
0x180081a22  mov     edx, 11Dh
0x180081a27  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x180081a2e  call    WPP_SF_s
0x180081a33  mov     r8d, 601h; Count
0x180081a39  lea     rdx, [rbp+0BF0h+Source]; Source
0x180081a40  lea     rcx, [rbp+0BF0h+Destination]; Destination
0x180081a44  call    strncpy_0
0x180081a49  or      ecx, 0FFFFFFFFh
0x180081a4c  lea     rax, [rbp+0BF0h+Source]
0x180081a53  mov     [rsp+0CF0h+cchCount2], ecx; cchCount2
0x180081a57  lea     r8, aIsdn_0; "isdn"
0x180081a5e  mov     r9d, ecx; cchCount1
0x180081a61  mov     [rsp+0CF0h+lpString2], rax; lpString2
0x180081a66  mov     ecx, 7Fh; Locale
0x180081a6b  mov     edx, esi; dwCmpFlags
0x180081a6d  call    cs:__imp_CompareStringA
0x180081a73  cmp     eax, edi
0x180081a75  jnz     loc_180081C27
0x180081a7b  lea     rcx, [rbp+0BF0h+Source]
0x180081a82  mov     rax, rbx
0x180081a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081a8a  mov     [r14+20h], rax
0x180081a8e  lea     rcx, [rbp+0BF0h+Destination]
0x180081a92  mov     [rsp+0CF0h+var_CC0], rcx
0x180081a97  lea     rax, [r14+0A8h]
0x180081a9e  mov     qword ptr [rsp+0CF0h+cchCount2], rax
0x180081aa3  mov     r12d, 6
0x180081aa9  mov     eax, [rsp+0CF0h+var_CA4]
0x180081aad  mov     rcx, r15
0x180081ab0  mov     dword ptr [rsp+0CF0h+lpString2], eax
0x180081ab4  mov     [r14+28h], r12d
0x180081ab8  call    RegReadPhoneList
0x180081abd  mov     ebx, eax
0x180081abf  test    eax, eax
0x180081ac1  jnz     loc_1800827CD
0x180081ac7  lea     r8, [r14+0B0h]
0x180081ace  mov     rcx, r15; hkey
0x180081ad1  lea     r9, [rbp+0BF0h+Destination]
0x180081ad5  lea     rdx, aLastselectedph; "LastSelectedPhone"
0x180081adc  call    RegReadLong
0x180081ae1  mov     ebx, eax
0x180081ae3  test    eax, eax
0x180081ae5  jnz     loc_180082773
0x180081aeb  lea     r8, [r14+0B4h]
0x180081af2  mov     rcx, r15
0x180081af5  lea     r9, [rbp+0BF0h+Destination]
0x180081af9  lea     rdx, aPromotealterna; "PromoteAlternates"
0x180081b00  call    RegReadFlag
0x180081b05  mov     ebx, eax
0x180081b07  test    eax, eax
0x180081b09  jnz     loc_18008270A
0x180081b0f  lea     r8, [r14+0B8h]
0x180081b16  mov     rcx, r15
0x180081b19  lea     r9, [rbp+0BF0h+Destination]
0x180081b1d  lea     rdx, aTrynextalterna; "TryNextAlternateOnFail"
0x180081b24  call    RegReadFlag
0x180081b29  mov     ebx, eax
0x180081b2b  test    eax, eax
0x180081b2d  jnz     loc_1800826A1
0x180081b33  lea     r12, [r14+84h]
0x180081b3a  mov     rcx, r15; hkey
0x180081b3d  mov     r8, r12
0x180081b40  lea     r9, [rbp+0BF0h+Destination]
0x180081b44  lea     rdx, aLinetype; "LineType"
0x180081b4b  call    RegReadLong
0x180081b50  mov     ebx, eax
0x180081b52  xor     eax, eax
0x180081b54  test    ebx, ebx
0x180081b56  jnz     loc_180082638
0x180081b5c  cmp     [r12], edi
0x180081b60  jbe     short loc_180081B66
0x180081b62  mov     [r12], eax
0x180081b66  lea     r8, [r14+88h]
0x180081b6d  mov     rcx, r15
0x180081b70  lea     r9, [rbp+0BF0h+Destination]
0x180081b74  lea     rdx, aFallback; "Fallback"
0x180081b7b  call    RegReadFlag
0x180081b80  mov     ebx, eax
0x180081b82  test    eax, eax
0x180081b84  jnz     loc_1800825CF
0x180081b8a  lea     r12, [r14+80h]
0x180081b91  mov     rcx, r15
0x180081b94  mov     r8, r12
0x180081b97  mov     [r12], esi
0x180081b9b  lea     r9, [rbp+0BF0h+Destination]
0x180081b9f  lea     rdx, aProprietary; "Proprietary"
0x180081ba6  call    RegReadFlag
0x180081bab  mov     ebx, eax
0x180081bad  test    eax, eax
0x180081baf  jnz     loc_180082566
0x180081bb5  lea     r9, [rbp+0BF0h+Destination]
0x180081bb9  mov     [rsp+0CF0h+var_CB0], 0FFFFFFFFh
0x180081bc1  lea     r8, [rsp+0CF0h+var_CB0]
0x180081bc6  mov     rcx, r15; hkey
0x180081bc9  lea     rdx, aChannelaggrega; "ChannelAggregation"
0x180081bd0  call    RegReadLong
0x180081bd5  xor     ecx, ecx
0x180081bd7  mov     ebx, eax
0x180081bd9  test    eax, eax
0x180081bdb  jnz     loc_1800824FD
0x180081be1  mov     eax, [rsp+0CF0h+var_CB0]
0x180081be5  cmp     eax, 0FFFFFFFFh
0x180081be8  jnz     short loc_180081BF0
0x180081bea  mov     [r12], ecx
0x180081bee  jmp     short loc_180081BF7
0x180081bf0  mov     [r14+90h], eax
0x180081bf7  lea     r8, [r14+8Ch]
0x180081bfe  mov     rcx, r15
0x180081c01  lea     r9, [rbp+0BF0h+Destination]
0x180081c05  lea     rdx, aEnablecompress; "EnableCompression"
0x180081c0c  call    RegReadFlag
0x180081c11  xor     ecx, ecx
0x180081c13  mov     ebx, eax
0x180081c15  test    eax, eax
0x180081c17  jnz     loc_180082494
0x180081c1d  mov     r12d, [rsp+0CF0h+var_CA0]
0x180081c22  jmp     loc_1800821C9
0x180081c27  or      ecx, 0FFFFFFFFh
0x180081c2a  lea     rax, [rbp+0BF0h+Source]
0x180081c31  mov     [rsp+0CF0h+cchCount2], ecx; cchCount2
0x180081c35  lea     r8, aModem_0; "modem"
0x180081c3c  mov     r9d, ecx; cchCount1
0x180081c3f  mov     [rsp+0CF0h+lpString2], rax; lpString2
0x180081c44  mov     ecx, 7Fh; Locale
0x180081c49  mov     edx, esi; dwCmpFlags
0x180081c4b  call    cs:__imp_CompareStringA
0x180081c51  cmp     eax, edi
0x180081c53  jnz     loc_180081E37
0x180081c59  lea     rcx, [rbp+0BF0h+Source]
0x180081c60  mov     rax, rbx
0x180081c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c68  mov     [r14+20h], rax
0x180081c6c  lea     rcx, [rbp+0BF0h+Destination]
0x180081c70  mov     [rsp+0CF0h+var_CC0], rcx
0x180081c75  lea     rax, [r14+0A8h]
0x180081c7c  mov     qword ptr [rsp+0CF0h+cchCount2], rax
0x180081c81  mov     rcx, r15
0x180081c84  mov     eax, [rsp+0CF0h+var_CA4]
0x180081c88  mov     dword ptr [rsp+0CF0h+lpString2], eax
0x180081c8c  mov     dword ptr [r14+28h], 3
0x180081c94  call    RegReadPhoneList
0x180081c99  xor     r12d, r12d
0x180081c9c  mov     ebx, eax
0x180081c9e  test    eax, eax
0x180081ca0  jnz     loc_180082B6C
0x180081ca6  lea     r8, [r14+0B0h]
0x180081cad  mov     rcx, r15; hkey
0x180081cb0  lea     r9, [rbp+0BF0h+Destination]
0x180081cb4  lea     rdx, aLastselectedph; "LastSelectedPhone"
0x180081cbb  call    RegReadLong
0x180081cc0  mov     ebx, eax
0x180081cc2  test    eax, eax
0x180081cc4  jnz     loc_180082B03
0x180081cca  lea     r8, [r14+0B4h]
0x180081cd1  mov     rcx, r15
0x180081cd4  lea     r9, [rbp+0BF0h+Destination]
0x180081cd8  lea     rdx, aPromotealterna; "PromoteAlternates"
0x180081cdf  call    RegReadFlag
0x180081ce4  mov     ebx, eax
0x180081ce6  test    eax, eax
0x180081ce8  jnz     loc_180082A9A
0x180081cee  lea     r8, [r14+0B8h]
0x180081cf5  mov     rcx, r15
0x180081cf8  lea     r9, [rbp+0BF0h+Destination]
0x180081cfc  lea     rdx, aTrynextalterna; "TryNextAlternateOnFail"
0x180081d03  call    RegReadFlag
0x180081d08  mov     ebx, eax
0x180081d0a  test    eax, eax
0x180081d0c  jnz     loc_180082A31
0x180081d12  lea     r8, [r14+6Ch]
0x180081d16  mov     rcx, r15
0x180081d19  lea     r9, [rbp+0BF0h+Destination]
0x180081d1d  lea     rdx, aHwflowcontrol; "HwFlowControl"
0x180081d24  call    RegReadFlag
0x180081d29  mov     ebx, eax
0x180081d2b  test    eax, eax
0x180081d2d  jnz     loc_1800829C8
0x180081d33  lea     r8, [r14+70h]
0x180081d37  mov     rcx, r15
0x180081d3a  lea     r9, [rbp+0BF0h+Destination]
0x180081d3e  lea     rdx, aProtocol; "Protocol"
0x180081d45  call    RegReadFlag
0x180081d4a  mov     ebx, eax
0x180081d4c  test    eax, eax
0x180081d4e  jnz     loc_18008295F
0x180081d54  lea     r8, [r14+74h]
0x180081d58  mov     rcx, r15
0x180081d5b  lea     r9, [rbp+0BF0h+Destination]
0x180081d5f  lea     rdx, aCompression; "Compression"
0x180081d66  call    RegReadFlag
0x180081d6b  mov     ebx, eax
0x180081d6d  test    eax, eax
0x180081d6f  jnz     loc_1800828F6
0x180081d75  mov     rcx, [rbp+0BF0h+arg_30]
0x180081d7c  lea     r8, [r14+78h]
0x180081d80  test    rcx, rcx
0x180081d83  jz      short loc_180081D93
0x180081d85  cmp     [rcx], r12d
0x180081d88  mov     eax, r12d
0x180081d8b  setz    al
0x180081d8e  mov     [r8], eax
0x180081d91  jmp     short loc_180081DB0
0x180081d93  lea     r9, [rbp+0BF0h+Destination]
0x180081d97  mov     rcx, r15
0x180081d9a  lea     rdx, aSpeaker; "Speaker"
0x180081da1  call    RegReadFlag
0x180081da6  mov     ebx, eax
0x180081da8  test    eax, eax
0x180081daa  jnz     loc_180082891
0x180081db0  lea     r8, [r14+7Ch]
0x180081db4  mov     rcx, r15; hkey
0x180081db7  lea     r9, [rbp+0BF0h+Destination]
0x180081dbb  lea     rdx, aMdmprotocol; "MdmProtocol"
0x180081dc2  call    RegReadLong
0x180081dc7  mov     ebx, eax
  ... truncated ...
```

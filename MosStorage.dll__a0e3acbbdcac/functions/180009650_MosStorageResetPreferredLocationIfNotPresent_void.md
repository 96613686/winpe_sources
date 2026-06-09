# MosStorageResetPreferredLocationIfNotPresent(void)

- ea: `0x180009650`
- end: `0x180009780`
- name: `?MosStorageResetPreferredLocationIfNotPresent@@YAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180006c44`
- `0x180009010`
- `0x180009650`
- `0x18000c9bc`
- `0x18000cb1c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000974a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000974a`

## string_xrefs

- `0x18000971f`: `MapsRepairAttempts`

## pseudocode

```c
__int64 __fastcall MosStorageResetPreferredLocationIfNotPresent(__int64 a1, __int64 a2, __int64 a3)
{
  int MapsPersistedRegString; // eax
  int v4; // r8d
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  _BYTE v10[1648]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v11[2]; // [rsp+690h] [rbp+590h] BYREF
  __int64 v12; // [rsp+6A0h] [rbp+5A0h]
  unsigned __int64 v13; // [rsp+6A8h] [rbp+5A8h]

  *(_OWORD *)v11 = 0;
  v12 = 0;
  v13 = 7;
  LOWORD(v11[0]) = 0;
  MapsPersistedRegString = RegUtils::GetMapsPersistedRegString(a1, a2, a3, (__int64)v11);
  if ( MapsPersistedRegString < 0 )
  {
    v4 = 629;
LABEL_14:
    v5 = ZTraceReportPropagationNoThis(MapsPersistedRegString, "MosStorageResetPreferredLocationIfNotPresent", v4);
    goto LABEL_15;
  }
  if ( !v12 )
    goto LABEL_4;
  memset_0(v10, 0, sizeof(v10));
  v6 = (const unsigned __int16 *)v11;
  if ( v13 > 7 )
    v6 = v11[0];
  MapsPersistedRegString = MosStorageGetStorageDeviceDataFromDeviceGuid(v6, (struct _STORAGE_DEVICE_DATA *)v10);
  v5 = MapsPersistedRegString;
  if ( MapsPersistedRegString == -2147023728 )
  {
    MapsPersistedRegString = RegUtils::DeleteMapsPersistedRegValue(v7, L"MapsPreferredDeviceGuid");
    if ( MapsPersistedRegString < 0 )
    {
      v4 = 640;
      goto LABEL_14;
    }
    MapsPersistedRegString = RegUtils::DeleteMapsPersistedRegValue(v8, L"MapsRepairAttempts");
    if ( MapsPersistedRegString < 0 )
    {
      v4 = 641;
      goto LABEL_14;
    }
LABEL_4:
    v5 = 0;
    goto LABEL_15;
  }
  if ( MapsPersistedRegString < 0 )
  {
    v4 = 644;
    goto LABEL_14;
  }
LABEL_15:
  std::wstring::~wstring((char **)v11);
  return v5;
}

```

## disassembly

```asm
0x180009650  mov     [rsp-8+arg_0], rbx
0x180009655  push    rbp
0x180009656  lea     rbp, [rsp-5C0h]
0x18000965e  sub     rsp, 6C0h
0x180009665  mov     rax, cs:__security_cookie
0x18000966c  xor     rax, rsp
0x18000966f  mov     [rbp+5C0h+var_10], rax
0x180009676  xorps   xmm0, xmm0
0x180009679  movups  xmmword ptr [rbp+5C0h+var_30], xmm0
0x180009680  mov     [rbp+5C0h+var_20], 0
0x18000968b  mov     [rbp+5C0h+var_18], 7
0x180009696  xor     eax, eax
0x180009698  mov     word ptr [rbp+5C0h+var_30], ax
0x18000969f  lea     r9, [rbp+5C0h+var_30]
0x1800096a6  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x1800096ab  test    eax, eax
0x1800096ad  jns     short loc_1800096BA
0x1800096af  mov     r8d, 275h
0x1800096b5  jmp     loc_180009741
0x1800096ba  cmp     [rbp+5C0h+var_20], 0
0x1800096c2  jnz     short loc_1800096CB
0x1800096c4  xor     ebx, ebx
0x1800096c6  jmp     loc_180009752
0x1800096cb  xor     edx, edx; Val
0x1800096cd  mov     r8d, 670h; Size
0x1800096d3  lea     rcx, [rsp+6C0h+var_6A0]; void *
0x1800096d8  call    memset_0
0x1800096dd  lea     rcx, [rbp+5C0h+var_30]
0x1800096e4  cmp     [rbp+5C0h+var_18], 7
0x1800096ec  cmova   rcx, [rbp+5C0h+var_30]; unsigned __int16 *
0x1800096f4  lea     rdx, [rsp+6C0h+var_6A0]; struct _STORAGE_DEVICE_DATA *
0x1800096f9  call    ?MosStorageGetStorageDeviceDataFromDeviceGuid@@YAJPEBGPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetStorageDeviceDataFromDeviceGuid(ushort const *,_STORAGE_DEVICE_DATA *)
0x1800096fe  mov     ebx, eax
0x180009700  cmp     eax, 80070490h
0x180009705  jnz     short loc_180009737
0x180009707  lea     rdx, ValueName; "MapsPreferredDeviceGuid"
0x18000970e  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180009713  test    eax, eax
0x180009715  jns     short loc_18000971F
0x180009717  mov     r8d, 280h
0x18000971d  jmp     short loc_180009741
0x18000971f  lea     rdx, aMapsrepairatte; "MapsRepairAttempts"
0x180009726  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18000972b  test    eax, eax
0x18000972d  jns     short loc_1800096C4
0x18000972f  mov     r8d, 281h
0x180009735  jmp     short loc_180009741
0x180009737  test    eax, eax
0x180009739  jns     short loc_180009752
0x18000973b  mov     r8d, 284h
0x180009741  lea     rdx, aMosstoragerese_2; "MosStorageResetPreferredLocationIfNotPr"...
0x180009748  mov     ecx, eax
0x18000974a  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009750  mov     ebx, eax
0x180009752  lea     rcx, [rbp+5C0h+var_30]
0x180009759  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000975e  mov     eax, ebx
0x180009760  mov     rcx, [rbp+5C0h+var_10]
0x180009767  xor     rcx, rsp; StackCookie
0x18000976a  call    __security_check_cookie
0x18000976f  mov     rbx, [rsp+6C0h+arg_0]
0x180009777  add     rsp, 6C0h
0x18000977e  pop     rbp
0x18000977f  retn
```

# MosStorageResetPreferredLocationIfDefined(void)

- ea: `0x180009590`
- end: `0x18000963d`
- name: `?MosStorageResetPreferredLocationIfDefined@@YAJXZ`
- size: `173`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180001c80`
- `0x180006c44`
- `0x180009590`
- `0x18000c9bc`
- `0x18000cb1c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009616`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180009616`

## string_xrefs

- `0x1800095f7`: `MapsRepairAttempts`

## pseudocode

```c
__int64 __fastcall MosStorageResetPreferredLocationIfDefined(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  int MapsPersistedRegString; // eax
  __int64 v5; // rcx
  int v6; // r8d
  __int64 v7; // rcx
  __int128 v9; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+30h] [rbp-28h]
  __int64 v11; // [rsp+38h] [rbp-20h]

  v9 = 0;
  v3 = 0;
  v10 = 0;
  v11 = 7;
  LOWORD(v9) = 0;
  MapsPersistedRegString = RegUtils::GetMapsPersistedRegString(a1, a2, a3, (__int64)&v9);
  if ( MapsPersistedRegString < 0 )
  {
    v6 = 613;
LABEL_8:
    v3 = ZTraceReportPropagationNoThis(MapsPersistedRegString, "MosStorageResetPreferredLocationIfDefined", v6);
    goto LABEL_9;
  }
  if ( v10 )
  {
    MapsPersistedRegString = RegUtils::DeleteMapsPersistedRegValue(v5, L"MapsPreferredDeviceGuid");
    if ( MapsPersistedRegString < 0 )
    {
      v6 = 616;
      goto LABEL_8;
    }
    MapsPersistedRegString = RegUtils::DeleteMapsPersistedRegValue(v7, L"MapsRepairAttempts");
    if ( MapsPersistedRegString < 0 )
    {
      v6 = 617;
      goto LABEL_8;
    }
  }
LABEL_9:
  std::wstring::~wstring((char **)&v9);
  return v3;
}

```

## disassembly

```asm
0x180009590  push    rbx
0x180009592  sub     rsp, 50h
0x180009596  mov     rax, cs:__security_cookie
0x18000959d  xor     rax, rsp
0x1800095a0  mov     [rsp+58h+var_18], rax
0x1800095a5  xorps   xmm0, xmm0
0x1800095a8  movups  [rsp+58h+var_38], xmm0
0x1800095ad  xor     ebx, ebx
0x1800095af  mov     [rsp+58h+var_28], rbx
0x1800095b4  mov     [rsp+58h+var_20], 7
0x1800095bd  mov     word ptr [rsp+58h+var_38], bx
0x1800095c2  lea     r9, [rsp+58h+var_38]
0x1800095c7  call    ?GetMapsPersistedRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsPersistedRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x1800095cc  test    eax, eax
0x1800095ce  jns     short loc_1800095D8
0x1800095d0  mov     r8d, 265h
0x1800095d6  jmp     short loc_18000960D
0x1800095d8  cmp     [rsp+58h+var_28], rbx
0x1800095dd  jz      short loc_18000961E
0x1800095df  lea     rdx, ValueName; "MapsPreferredDeviceGuid"
0x1800095e6  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x1800095eb  test    eax, eax
0x1800095ed  jns     short loc_1800095F7
0x1800095ef  mov     r8d, 268h
0x1800095f5  jmp     short loc_18000960D
0x1800095f7  lea     rdx, aMapsrepairatte; "MapsRepairAttempts"
0x1800095fe  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x180009603  test    eax, eax
0x180009605  jns     short loc_18000961E
0x180009607  mov     r8d, 269h
0x18000960d  lea     rdx, aMosstoragerese_3; "MosStorageResetPreferredLocationIfDefin"...
0x180009614  mov     ecx, eax
0x180009616  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000961c  mov     ebx, eax
0x18000961e  lea     rcx, [rsp+58h+var_38]
0x180009623  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009628  mov     eax, ebx
0x18000962a  mov     rcx, [rsp+58h+var_18]
0x18000962f  xor     rcx, rsp; StackCookie
0x180009632  call    __security_check_cookie
0x180009637  add     rsp, 50h
0x18000963b  pop     rbx
0x18000963c  retn
```

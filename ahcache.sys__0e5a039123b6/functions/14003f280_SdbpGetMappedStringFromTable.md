# SdbpGetMappedStringFromTable

- ea: `0x14003f280`
- end: `0x14003f567`
- name: `SdbpGetMappedStringFromTable`
- size: `743`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003ef10`

## callees

- `0x1400055d4`
- `0x14003e248`
- `0x14003e364`
- `0x14003f280`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14003f2c6`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14003f2c6`

## string_xrefs

- `0x14003f471`: `Error reading data`
- `0x14003f522`: `Trying to read mapped data past the end of the database offset 0x%x size 0x%x`
- `0x14003f4ad`: `Error reading tag`

## pseudocode

```c
__int64 __fastcall SdbpGetMappedStringFromTable(__int64 Parameter, int a2)
{
  bool v2; // zf
  __int64 v4; // rbx
  int v5; // r14d
  NTSTATUS v6; // eax
  int v7; // eax
  unsigned int v8; // esi
  int v9; // ebp
  __int64 v10; // rdi
  __int64 v11; // rbx
  unsigned int v13; // ecx
  unsigned int v14; // eax
  unsigned __int16 v15; // [rsp+50h] [rbp+8h] BYREF
  PVOID Context; // [rsp+60h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(Parameter + 16) == 0;
  v4 = Parameter;
  Context = 0;
  v5 = 6;
  if ( v2 )
  {
    v6 = RtlRunOnceExecuteOnce(
           (PRTL_RUN_ONCE)(Parameter + 2624),
           InitOnceGetStringTableOffset,
           (PVOID)Parameter,
           &Context);
    if ( v6 < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbpGetStringTableItemFromStringRef",
        858,
        "RtlRunOnceExecuteOnce failed for InitOnceGetStringTableOffset [%x]",
        v6);
LABEL_9:
      AslLogCallPrintf(
        1,
        "SdbpGetMappedStringFromTable",
        977,
        "SdbpGetStringTableItemFromStringRef failed to get tagid for string ref");
      return 0;
    }
    if ( !Context || (v7 = *(_DWORD *)Context) == 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbpGetStringTableItemFromStringRef",
        874,
        "InitOnceGetStringTableOffset succeeded but failed to find string table");
      goto LABEL_9;
    }
  }
  else
  {
    v4 = *(_QWORD *)(Parameter + 2640);
    if ( !v4 )
    {
      AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 838, "No stringtable in DB");
      goto LABEL_9;
    }
    v7 = 6;
  }
  v8 = v7 + a2;
  v9 = 2;
  v15 = 0;
  if ( !(unsigned int)SdbpReadMappedData(v4, v7 + a2, &v15, 2u) )
  {
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    goto LABEL_32;
  }
  if ( v15 != 0x8801 )
  {
LABEL_32:
    AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 888, "Pulled out a non-stringtable item");
    goto LABEL_9;
  }
  v10 = v4;
  v11 = 0;
  if ( !v8 || !v10 )
    goto LABEL_9;
  v15 = 0;
  if ( !(unsigned int)SdbpReadMappedData(v10, v8, &v15, 2u) )
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
    v9 = 0;
    goto LABEL_15;
  }
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (v15 & 0xF000u) < 0x7000 )
      v5 = 2;
    goto LABEL_14;
  }
  v14 = v15 & 0xF000;
  if ( v14 == 36864 )
  {
LABEL_14:
    v9 = v5;
    goto LABEL_15;
  }
  if ( v14 != 24576 )
  {
    if ( v14 > 0x4000 )
    {
      if ( v14 == 20480 )
        goto LABEL_15;
      if ( v14 == 28672 || v14 == 0x8000 )
        goto LABEL_14;
      goto LABEL_38;
    }
    if ( v14 != 0x4000 && v14 != 4096 && v14 != 0x2000 && v14 != 12288 )
    {
LABEL_38:
      AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v15);
      v9 = 0;
    }
  }
LABEL_15:
  v13 = *(_DWORD *)(v10 + 20);
  if ( v8 + v9 >= v13 )
  {
    AslLogCallPrintf(
      1,
      "SdbpGetMappedData",
      915,
      "Trying to read mapped data past the end of the database offset 0x%x size 0x%x",
      v8 + v9,
      v13);
    goto LABEL_40;
  }
  v11 = v8 + v9 + *(_QWORD *)(v10 + 8);
  if ( !v11 )
LABEL_40:
    AslLogCallPrintf(1, "SdbpGetMappedTagData", 550, "Error getting ptr to tag data");
  return v11;
}

```

## disassembly

```asm
0x14003f280  mov     [rsp+arg_8], rbx
0x14003f285  mov     [rsp+arg_18], rbp
0x14003f28a  push    rsi
0x14003f28b  push    rdi
0x14003f28c  push    r14
0x14003f28e  sub     rsp, 30h
0x14003f292  cmp     dword ptr [rcx+10h], 0
0x14003f296  mov     edi, edx
0x14003f298  mov     rbx, rcx
0x14003f29b  mov     [rsp+48h+Context], 0
0x14003f2a4  mov     r14d, 6
0x14003f2aa  jnz     loc_14003F43A
0x14003f2b0  add     rcx, 0A40h; RunOnce
0x14003f2b7  lea     r9, [rsp+48h+Context]; Context
0x14003f2bc  mov     r8, rbx; Parameter
0x14003f2bf  lea     rdx, InitOnceGetStringTableOffset; InitFn
0x14003f2c6  call    cs:__imp_RtlRunOnceExecuteOnce
0x14003f2cd  nop     dword ptr [rax+rax+00h]
0x14003f2d2  test    eax, eax
0x14003f2d4  js      loc_14003F413
0x14003f2da  mov     rax, [rsp+48h+Context]
0x14003f2df  test    rax, rax
0x14003f2e2  jz      loc_14003F44E
0x14003f2e8  mov     eax, [rax]
0x14003f2ea  test    eax, eax
0x14003f2ec  jz      loc_14003F44E
0x14003f2f2  lea     esi, [rax+rdi]
0x14003f2f5  mov     ebp, 2
0x14003f2fa  xor     eax, eax
0x14003f2fc  lea     r8, [rsp+48h+arg_0]
0x14003f301  mov     r9d, ebp
0x14003f304  mov     [rsp+48h+arg_0], ax
0x14003f309  mov     edx, esi
0x14003f30b  mov     rcx, rbx
0x14003f30e  call    SdbpReadMappedData
0x14003f313  test    eax, eax
0x14003f315  jz      loc_14003F471
0x14003f31b  mov     eax, 8801h
0x14003f320  cmp     [rsp+48h+arg_0], ax
0x14003f325  jnz     loc_14003F48F
0x14003f32b  mov     rdi, rbx
0x14003f32e  xor     ebx, ebx
0x14003f330  test    esi, esi
0x14003f332  jz      short loc_14003F339
0x14003f334  test    rdi, rdi
0x14003f337  jnz     short loc_14003F36D
0x14003f339  lea     r9, aSdbpgetstringt; "SdbpGetStringTableItemFromStringRef fai"...
0x14003f340  mov     r8d, 3D1h
0x14003f346  lea     rdx, aSdbpgetmappeds; "SdbpGetMappedStringFromTable"
0x14003f34d  mov     ecx, 1
0x14003f352  call    AslLogCallPrintf
0x14003f357  xor     eax, eax
0x14003f359  mov     rbx, [rsp+48h+arg_8]
0x14003f35e  mov     rbp, [rsp+48h+arg_18]
0x14003f363  add     rsp, 30h
0x14003f367  pop     r14
0x14003f369  pop     rdi
0x14003f36a  pop     rsi
0x14003f36b  retn
0x14003f36d  xor     eax, eax
0x14003f36f  lea     r8, [rsp+48h+arg_0]
0x14003f374  mov     r9d, ebp
0x14003f377  mov     [rsp+48h+arg_0], ax
0x14003f37c  mov     edx, esi
0x14003f37e  mov     rcx, rdi
0x14003f381  call    SdbpReadMappedData
0x14003f386  test    eax, eax
0x14003f388  jz      loc_14003F4AD
0x14003f38e  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003f393  mov     ecx, 0F000h
0x14003f398  test    eax, eax
0x14003f39a  jnz     short loc_14003F3D5
0x14003f39c  movzx   eax, [rsp+48h+arg_0]
0x14003f3a1  and     ax, cx
0x14003f3a4  mov     ecx, 7000h
0x14003f3a9  cmp     ax, cx
0x14003f3ac  cmovb   r14d, ebp
0x14003f3b0  mov     ebp, r14d
0x14003f3b3  mov     ecx, [rdi+14h]
0x14003f3b6  lea     eax, [rsi+rbp]
0x14003f3b9  cmp     eax, ecx
0x14003f3bb  jnb     loc_14003F51E
0x14003f3c1  mov     rbx, [rdi+8]
0x14003f3c5  mov     edx, eax
0x14003f3c7  add     rbx, rdx
0x14003f3ca  jz      loc_14003F544
0x14003f3d0  mov     rax, rbx
0x14003f3d3  jmp     short loc_14003F359
0x14003f3d5  movzx   edx, [rsp+48h+arg_0]
0x14003f3da  mov     eax, edx
0x14003f3dc  and     eax, ecx
0x14003f3de  cmp     eax, 9000h
0x14003f3e3  jz      short loc_14003F3B0
0x14003f3e5  cmp     eax, 6000h
0x14003f3ea  jz      short loc_14003F3B3
0x14003f3ec  cmp     eax, 4000h
0x14003f3f1  ja      loc_14003F4D2
0x14003f3f7  jz      short loc_14003F3B3
0x14003f3f9  cmp     eax, 1000h
0x14003f3fe  jz      short loc_14003F3B3
0x14003f400  cmp     eax, 2000h
0x14003f405  jz      short loc_14003F3B3
0x14003f407  cmp     eax, 3000h
0x14003f40c  jz      short loc_14003F3B3
0x14003f40e  jmp     loc_14003F4F5
0x14003f413  lea     r9, aRtlrunonceexec_0; "RtlRunOnceExecuteOnce failed for InitOn"...
0x14003f41a  mov     [rsp+48h+var_28], eax
0x14003f41e  mov     r8d, 35Ah
0x14003f424  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x14003f42b  mov     ecx, 1
0x14003f430  call    AslLogCallPrintf
0x14003f435  jmp     loc_14003F339
0x14003f43a  mov     rbx, [rcx+0A50h]
0x14003f441  test    rbx, rbx
0x14003f444  jz      short loc_14003F49E
0x14003f446  mov     eax, r14d
0x14003f449  jmp     loc_14003F2F2
0x14003f44e  lea     r9, aInitoncegetstr_0; "InitOnceGetStringTableOffset succeeded "...
0x14003f455  mov     r8d, 36Ah
0x14003f45b  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x14003f462  mov     ecx, 1
0x14003f467  call    AslLogCallPrintf
0x14003f46c  jmp     loc_14003F339
0x14003f471  lea     r9, aErrorReadingDa; "Error reading data"
0x14003f478  mov     r8d, 0BDFh
0x14003f47e  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003f485  mov     ecx, 1
0x14003f48a  call    AslLogCallPrintf
0x14003f48f  lea     r9, aPulledOutANonS; "Pulled out a non-stringtable item"
0x14003f496  mov     r8d, 378h
0x14003f49c  jmp     short loc_14003F45B
0x14003f49e  lea     r9, aNoStringtableI; "No stringtable in DB"
0x14003f4a5  mov     r8d, 346h
0x14003f4ab  jmp     short loc_14003F45B
0x14003f4ad  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x14003f4b4  mov     r8d, 64h ; 'd'
0x14003f4ba  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003f4c1  mov     ecx, 1
0x14003f4c6  call    AslLogCallPrintf
0x14003f4cb  xor     ebp, ebp
0x14003f4cd  jmp     loc_14003F3B3
0x14003f4d2  cmp     eax, 5000h
0x14003f4d7  jz      loc_14003F3B3
0x14003f4dd  mov     ecx, 7000h
0x14003f4e2  cmp     eax, ecx
0x14003f4e4  jz      loc_14003F3B0
0x14003f4ea  cmp     eax, 8000h
0x14003f4ef  jz      loc_14003F3B0
0x14003f4f5  mov     [rsp+48h+var_28], edx
0x14003f4f9  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x14003f500  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x14003f507  mov     r8d, 79h ; 'y'
0x14003f50d  mov     ecx, 1
0x14003f512  call    AslLogCallPrintf
0x14003f517  xor     ebp, ebp
0x14003f519  jmp     loc_14003F3B3
0x14003f51e  mov     [rsp+48h+var_20], ecx
0x14003f522  lea     r9, aTryingToReadMa; "Trying to read mapped data past the end"...
0x14003f529  mov     ecx, 1
0x14003f52e  mov     [rsp+48h+var_28], eax
0x14003f532  mov     r8d, 393h
0x14003f538  lea     rdx, aSdbpgetmappedd; "SdbpGetMappedData"
0x14003f53f  call    AslLogCallPrintf
0x14003f544  lea     r9, aErrorGettingPt; "Error getting ptr to tag data"
0x14003f54b  mov     r8d, 226h
0x14003f551  lea     rdx, aSdbpgetmappedt_0; "SdbpGetMappedTagData"
0x14003f558  mov     ecx, 1
0x14003f55d  call    AslLogCallPrintf
0x14003f562  jmp     loc_14003F3D0
```

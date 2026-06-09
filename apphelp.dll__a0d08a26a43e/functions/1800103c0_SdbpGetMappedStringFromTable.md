# SdbpGetMappedStringFromTable

- ea: `0x1800103c0`
- end: `0x1800106eb`
- name: `SdbpGetMappedStringFromTable`
- size: `811`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004513c`
- `0x180045adc`

## callees

- `0x18000ef24`
- `0x18000f080`
- `0x18000f114`
- `0x1800103c0`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x1800103ff`
- `ntdll!RtlRunOnceExecuteOnce` at `0x1800103ff`

## string_xrefs

- `0x180010498`: `SdbpReadMappedData`
- `0x18001061e`: `SdbpReadMappedData`
- `0x1800104a9`: `Error reading data`
- `0x18001062f`: `Error reading tag`
- `0x1800106a4`: `Trying to read mapped data past the end of the database offset 0x%x size 0x%x`
- `0x180010600`: `Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)`

## pseudocode

```c
__int64 __fastcall SdbpGetMappedStringFromTable(__int64 a1, int a2)
{
  bool v2; // zf
  __int64 v4; // rbx
  int v5; // ebp
  int v6; // eax
  int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // ecx
  __int64 v10; // rdi
  int v11; // ebx
  int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // ecx
  __int64 v16; // rbx
  unsigned __int16 v17; // [rsp+60h] [rbp+8h] BYREF
  int *v18; // [rsp+70h] [rbp+18h] BYREF

  v2 = *(_DWORD *)(a1 + 16) == 0;
  v4 = a1;
  v18 = 0;
  v5 = 6;
  if ( !v2 )
  {
    v4 = *(_QWORD *)(a1 + 2640);
    if ( v4 )
    {
      v7 = 6;
      goto LABEL_5;
    }
    AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 838, "No stringtable in DB");
LABEL_10:
    AslLogCallPrintf(
      1,
      "SdbpGetMappedStringFromTable",
      977,
      "SdbpGetStringTableItemFromStringRef failed to get tagid for string ref");
    return 0;
  }
  v6 = RtlRunOnceExecuteOnce(a1 + 2624, InitOnceGetStringTableOffset, a1, &v18);
  if ( v6 < 0 )
  {
    AslLogCallPrintf(
      1,
      "SdbpGetStringTableItemFromStringRef",
      858,
      "RtlRunOnceExecuteOnce failed for InitOnceGetStringTableOffset [%x]",
      v6);
    goto LABEL_10;
  }
  if ( !v18 || (v7 = *v18) == 0 )
  {
    AslLogCallPrintf(
      1,
      "SdbpGetStringTableItemFromStringRef",
      874,
      "InitOnceGetStringTableOffset succeeded but failed to find string table");
    goto LABEL_10;
  }
LABEL_5:
  v8 = (unsigned int)(v7 + a2);
  if ( (unsigned int)v8 >= 0xFFFFFFFE )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      855,
      "Offset and region size add up to cause an integer overflow or underflow");
LABEL_12:
    AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
    goto LABEL_13;
  }
  v9 = *(_DWORD *)(v4 + 20);
  if ( v9 < (int)v8 + 2 )
  {
    AslLogCallPrintf(
      1,
      "SdbpReadMappedData",
      860,
      "Attempt to read past the end of the database offset 0x%lx size 0x%lx (0x%lx)",
      v8,
      2,
      v9);
    goto LABEL_12;
  }
  if ( *(_WORD *)(v8 + *(_QWORD *)(v4 + 8)) != 0x8801 )
  {
LABEL_13:
    AslLogCallPrintf(1, "SdbpGetStringTableItemFromStringRef", 888, "Pulled out a non-stringtable item");
    goto LABEL_10;
  }
  v10 = v4;
  v11 = v8;
  if ( !(_DWORD)v8 || !v10 )
    goto LABEL_10;
  v13 = 2;
  v17 = 0;
  if ( !(unsigned int)SdbpReadMappedData(v10, v8, &v17, 2) )
  {
    AslLogCallPrintf(1, "SdbpGetTagHeadSize", 100, "Error reading tag");
    v13 = 0;
    goto LABEL_20;
  }
  if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( (v17 & 0xF000u) < 0x7000 )
      v5 = 2;
    goto LABEL_19;
  }
  v14 = v17 & 0xF000;
  if ( v14 == 36864 )
  {
LABEL_19:
    v13 = v5;
    goto LABEL_20;
  }
  if ( v14 != 24576 )
  {
    if ( v14 > 0x4000 )
    {
      if ( v14 == 20480 )
        goto LABEL_20;
      if ( v14 == 28672 || v14 == 0x8000 )
        goto LABEL_19;
      goto LABEL_42;
    }
    if ( v14 != 0x4000 && v14 != 4096 && v14 != 0x2000 && v14 != 12288 )
    {
LABEL_42:
      AslLogCallPrintf(1, "SdbpGetTagHeadSize", 121, "Invalid TAG_TYPE encountered. TAG: [%x]", v17);
      v13 = 0;
    }
  }
LABEL_20:
  v15 = *(_DWORD *)(v10 + 20);
  if ( v11 + v13 >= v15 )
  {
    AslLogCallPrintf(
      1,
      "SdbpGetMappedData",
      915,
      "Trying to read mapped data past the end of the database offset 0x%x size 0x%x",
      v11 + v13,
      v15);
    v16 = 0;
    goto LABEL_44;
  }
  v16 = (unsigned int)(v11 + v13) + *(_QWORD *)(v10 + 8);
  if ( !v16 )
LABEL_44:
    AslLogCallPrintf(1, "SdbpGetMappedTagData", 550, "Error getting ptr to tag data");
  return v16;
}

```

## disassembly

```asm
0x1800103c0  mov     [rsp+arg_8], rbx
0x1800103c5  push    rbp
0x1800103c6  push    rsi
0x1800103c7  push    rdi
0x1800103c8  sub     rsp, 40h
0x1800103cc  cmp     dword ptr [rcx+10h], 0
0x1800103d0  mov     edi, edx
0x1800103d2  mov     rbx, rcx
0x1800103d5  mov     [rsp+58h+arg_10], 0
0x1800103de  mov     ebp, 6
0x1800103e3  jnz     loc_1800105D7
0x1800103e9  add     rcx, 0A40h
0x1800103f0  lea     r9, [rsp+58h+arg_10]
0x1800103f5  mov     r8, rbx
0x1800103f8  lea     rdx, InitOnceGetStringTableOffset
0x1800103ff  call    cs:__imp_RtlRunOnceExecuteOnce
0x180010405  test    eax, eax
0x180010407  js      loc_1800104EA
0x18001040d  mov     rax, [rsp+58h+arg_10]
0x180010412  test    rax, rax
0x180010415  jz      loc_1800105C5
0x18001041b  mov     eax, [rax]
0x18001041d  test    eax, eax
0x18001041f  jz      loc_1800105C5
0x180010425  lea     edx, [rax+rdi]
0x180010428  lea     eax, [rdx+2]
0x18001042b  cmp     eax, 2
0x18001042e  jb      short loc_18001048B
0x180010430  mov     ecx, [rbx+14h]
0x180010433  cmp     ecx, eax
0x180010435  jb      loc_1800105FC
0x18001043b  mov     rax, [rbx+8]
0x18001043f  mov     r8d, 8801h
0x180010445  cmp     [rdx+rax], r8w
0x18001044a  jnz     short loc_1800104C7
0x18001044c  mov     rdi, rbx
0x18001044f  mov     ebx, edx
0x180010451  test    edx, edx
0x180010453  jz      short loc_18001045E
0x180010455  test    rdi, rdi
0x180010458  jnz     loc_180010511
0x18001045e  lea     r9, aSdbpgetstringt; "SdbpGetStringTableItemFromStringRef fai"...
0x180010465  mov     r8d, 3D1h
0x18001046b  lea     rdx, aSdbpgetmappeds; "SdbpGetMappedStringFromTable"
0x180010472  mov     ecx, 1
0x180010477  call    AslLogCallPrintf
0x18001047c  xor     eax, eax
0x18001047e  mov     rbx, [rsp+58h+arg_8]
0x180010483  add     rsp, 40h
0x180010487  pop     rdi
0x180010488  pop     rsi
0x180010489  pop     rbp
0x18001048a  retn
0x18001048b  lea     r9, aOffsetAndRegio; "Offset and region size add up to cause "...
0x180010492  mov     r8d, 357h
0x180010498  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x18001049f  mov     ecx, 1
0x1800104a4  call    AslLogCallPrintf
0x1800104a9  lea     r9, aErrorReadingDa; "Error reading data"
0x1800104b0  mov     r8d, 0BDFh
0x1800104b6  lea     rdx, aSdbgettagfromt_1; "SdbGetTagFromTagID"
0x1800104bd  mov     ecx, 1
0x1800104c2  call    AslLogCallPrintf
0x1800104c7  lea     r9, aPulledOutANonS; "Pulled out a non-stringtable item"
0x1800104ce  mov     r8d, 378h
0x1800104d4  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x1800104db  mov     ecx, 1
0x1800104e0  call    AslLogCallPrintf
0x1800104e5  jmp     loc_18001045E
0x1800104ea  lea     r9, aRtlrunonceexec_0; "RtlRunOnceExecuteOnce failed for InitOn"...
0x1800104f1  mov     [rsp+58h+var_38], eax
0x1800104f5  mov     r8d, 35Ah
0x1800104fb  lea     rdx, aSdbpgetstringt_0; "SdbpGetStringTableItemFromStringRef"
0x180010502  mov     ecx, 1
0x180010507  call    AslLogCallPrintf
0x18001050c  jmp     loc_18001045E
0x180010511  xor     eax, eax
0x180010513  lea     r8, [rsp+58h+arg_0]
0x180010518  mov     esi, 2
0x18001051d  mov     [rsp+58h+arg_0], ax
0x180010522  mov     r9d, esi
0x180010525  mov     rcx, rdi
0x180010528  call    SdbpReadMappedData
0x18001052d  test    eax, eax
0x18001052f  jz      loc_18001062F
0x180010535  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18001053a  mov     ecx, 0F000h
0x18001053f  test    eax, eax
0x180010541  jz      short loc_1800105B0
0x180010543  movzx   edx, [rsp+58h+arg_0]
0x180010548  mov     eax, edx
0x18001054a  and     eax, ecx
0x18001054c  cmp     eax, 9000h
0x180010551  jnz     short loc_180010582
0x180010553  mov     esi, ebp
0x180010555  mov     ecx, [rdi+14h]
0x180010558  lea     eax, [rbx+rsi]
0x18001055b  cmp     eax, ecx
0x18001055d  jnb     loc_1800106A0
0x180010563  mov     rbx, [rdi+8]
0x180010567  mov     edx, eax
0x180010569  add     rbx, rdx
0x18001056c  jz      loc_1800106C8
0x180010572  mov     rax, rbx
0x180010575  mov     rbx, [rsp+58h+arg_8]
0x18001057a  add     rsp, 40h
0x18001057e  pop     rdi
0x18001057f  pop     rsi
0x180010580  pop     rbp
0x180010581  retn
0x180010582  cmp     eax, 6000h
0x180010587  jz      short loc_180010555
0x180010589  cmp     eax, 4000h
0x18001058e  ja      loc_180010654
0x180010594  jz      short loc_180010555
0x180010596  cmp     eax, 1000h
0x18001059b  jz      short loc_180010555
0x18001059d  cmp     eax, 2000h
0x1800105a2  jz      short loc_180010555
0x1800105a4  cmp     eax, 3000h
0x1800105a9  jz      short loc_180010555
0x1800105ab  jmp     loc_180010677
0x1800105b0  movzx   eax, [rsp+58h+arg_0]
0x1800105b5  and     ax, cx
0x1800105b8  mov     ecx, 7000h
0x1800105bd  cmp     ax, cx
0x1800105c0  cmovb   ebp, esi
0x1800105c3  jmp     short loc_180010553
0x1800105c5  lea     r9, aInitoncegetstr_0; "InitOnceGetStringTableOffset succeeded "...
0x1800105cc  mov     r8d, 36Ah
0x1800105d2  jmp     loc_1800104D4
0x1800105d7  mov     rbx, [rcx+0A50h]
0x1800105de  test    rbx, rbx
0x1800105e1  jz      short loc_1800105EA
0x1800105e3  mov     eax, ebp
0x1800105e5  jmp     loc_180010425
0x1800105ea  lea     r9, aNoStringtableI; "No stringtable in DB"
0x1800105f1  mov     r8d, 346h
0x1800105f7  jmp     loc_1800104D4
0x1800105fc  mov     [rsp+58h+var_28], ecx
0x180010600  lea     r9, aAttemptToReadP; "Attempt to read past the end of the dat"...
0x180010607  mov     [rsp+58h+var_30], 2
0x18001060f  mov     r8d, 35Ch
0x180010615  mov     [rsp+58h+var_38], edx
0x180010619  mov     ecx, 1
0x18001061e  lea     rdx, aSdbpreadmapped; "SdbpReadMappedData"
0x180010625  call    AslLogCallPrintf
0x18001062a  jmp     loc_1800104A9
0x18001062f  lea     r9, aErrorReadingTa_0; "Error reading tag"
0x180010636  mov     r8d, 64h ; 'd'
0x18001063c  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x180010643  mov     ecx, 1
0x180010648  call    AslLogCallPrintf
0x18001064d  xor     esi, esi
0x18001064f  jmp     loc_180010555
0x180010654  cmp     eax, 5000h
0x180010659  jz      loc_180010555
0x18001065f  mov     ecx, 7000h
0x180010664  cmp     eax, ecx
0x180010666  jz      loc_180010553
0x18001066c  cmp     eax, 8000h
0x180010671  jz      loc_180010553
0x180010677  mov     [rsp+58h+var_38], edx
0x18001067b  lea     r9, aInvalidTagType; "Invalid TAG_TYPE encountered. TAG: [%x]"
0x180010682  lea     rdx, aSdbpgettaghead; "SdbpGetTagHeadSize"
0x180010689  mov     r8d, 79h ; 'y'
0x18001068f  mov     ecx, 1
0x180010694  call    AslLogCallPrintf
0x180010699  xor     esi, esi
0x18001069b  jmp     loc_180010555
0x1800106a0  mov     [rsp+58h+var_30], ecx
0x1800106a4  lea     r9, aTryingToReadMa; "Trying to read mapped data past the end"...
0x1800106ab  mov     ecx, 1
0x1800106b0  mov     [rsp+58h+var_38], eax
0x1800106b4  mov     r8d, 393h
0x1800106ba  lea     rdx, aSdbpgetmappedd; "SdbpGetMappedData"
0x1800106c1  call    AslLogCallPrintf
0x1800106c6  xor     ebx, ebx
0x1800106c8  lea     r9, aErrorGettingPt; "Error getting ptr to tag data"
0x1800106cf  mov     r8d, 226h
0x1800106d5  lea     rdx, aSdbpgetmappedt_0; "SdbpGetMappedTagData"
0x1800106dc  mov     ecx, 1
0x1800106e1  call    AslLogCallPrintf
0x1800106e6  jmp     loc_180010572
```

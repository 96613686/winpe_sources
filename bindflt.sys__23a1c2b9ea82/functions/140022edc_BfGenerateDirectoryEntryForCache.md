# BfGenerateDirectoryEntryForCache

- ea: `0x140022edc`
- end: `0x14002329a`
- name: `BfGenerateDirectoryEntryForCache`
- size: `958`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140018b60`

## callees

- `0x140003140`
- `0x140004b90`
- `0x140004fc0`
- `0x140022edc`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x140022f4c`
- `FLTMGR!FltQueryInformationFile` at `0x140022f8b`
- `FLTMGR!FltQueryInformationFile` at `0x140022fc2`
- `FLTMGR!FltQueryInformationFile` at `0x140022f4c`
- `FLTMGR!FltQueryInformationFile` at `0x140022f8b`
- `FLTMGR!FltQueryInformationFile` at `0x140022fc2`

## pseudocode

```c
__int64 __fastcall BfGenerateDirectoryEntryForCache(__int64 a1)
{
  struct _FILE_OBJECT *v2; // rdx
  struct _FLT_INSTANCE *v3; // rcx
  int v4; // edx
  NTSTATUS InformationFile; // ebx
  NTSTATUS v6; // eax
  char v7; // r13
  char v8; // r12
  char v9; // r15
  char v10; // r14
  char v11; // si
  char v12; // r11
  char v13; // r10
  char v14; // r9
  char v15; // r8
  char v16; // dl
  char v17; // cl
  int v19; // r9d
  char v20; // [rsp+30h] [rbp-D0h]
  char v21; // [rsp+38h] [rbp-C8h]
  char v22; // [rsp+40h] [rbp-C0h]
  char v23; // [rsp+50h] [rbp-B0h]
  int v24; // [rsp+51h] [rbp-AFh]
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+70h] [rbp-90h]
  _QWORD FileInformation[14]; // [rsp+80h] [rbp-80h] BYREF

  memset(FileInformation, 0, 0x68u);
  v2 = *(struct _FILE_OBJECT **)(a1 + 104);
  v3 = *(struct _FLT_INSTANCE **)(a1 + 72);
  v27 = 0;
  v26 = 0;
  v25 = 0;
  InformationFile = FltQueryInformationFile(v3, v2, FileInformation, 0x68u, FileAllInformation, 0);
  if ( (int)(InformationFile + 0x80000000) < 0 || InformationFile == -2147483643 )
  {
    InformationFile = FltQueryInformationFile(
                        *(PFLT_INSTANCE *)(a1 + 72),
                        *(PFILE_OBJECT *)(a1 + 104),
                        &v25,
                        8u,
                        FileAttributeTagInformation,
                        0);
    if ( InformationFile < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = 35;
        v19 = 11;
        v21 = InformationFile;
        v20 = 63;
        goto LABEL_13;
      }
    }
    else
    {
      v6 = FltQueryInformationFile(
             *(PFLT_INSTANCE *)(a1 + 72),
             *(PFILE_OBJECT *)(a1 + 104),
             &v26,
             0x18u,
             FileMaximumInformation|FileBothDirectoryInformation,
             0);
      InformationFile = v6;
      if ( v6 == -1073741637 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v4) = 4;
          WPP_RECORDER_SF_sDdd(
            WPP_GLOBAL_Control->DeviceExtension,
            v4,
            12,
            12,
            (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
            76,
            187,
            59);
        }
        v17 = -1;
        v16 = -1;
        v23 = -1;
        v15 = -1;
        v24 = -1;
        v14 = -1;
        v13 = -1;
        v12 = -1;
        v11 = -1;
        v10 = -1;
        v9 = -1;
        v8 = -1;
        v7 = -1;
      }
      else
      {
        if ( v6 < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return (unsigned int)InformationFile;
          v22 = 59;
          v19 = 13;
          v21 = v6;
          v20 = 81;
          goto LABEL_13;
        }
        v7 = BYTE2(v27);
        v8 = BYTE1(v27);
        v9 = v27;
        v10 = HIBYTE(v26);
        v11 = BYTE14(v26);
        v12 = BYTE13(v26);
        v13 = BYTE12(v26);
        v14 = BYTE11(v26);
        v15 = BYTE10(v26);
        v16 = BYTE9(v26);
        v17 = BYTE8(v26);
        v24 = HIDWORD(v27);
        v23 = BYTE3(v27);
      }
      *(_QWORD *)(a1 + 200) = FileInformation[5];
      *(_QWORD *)(a1 + 184) = FileInformation[3];
      *(_QWORD *)(a1 + 160) = FileInformation[0];
      *(_DWORD *)(a1 + 216) = FileInformation[9];
      *(_QWORD *)(a1 + 192) = FileInformation[6];
      *(_DWORD *)(a1 + 208) = FileInformation[4];
      *(_QWORD *)(a1 + 168) = FileInformation[1];
      *(_QWORD *)(a1 + 176) = FileInformation[2];
      *(_DWORD *)(a1 + 220) = HIDWORD(v25);
      *(_BYTE *)(a1 + 243) = v23;
      *(_DWORD *)(a1 + 244) = v24;
      *(_QWORD *)(a1 + 224) = FileInformation[8];
      *(_BYTE *)(a1 + 232) = v17;
      *(_BYTE *)(a1 + 233) = v16;
      *(_BYTE *)(a1 + 234) = v15;
      *(_BYTE *)(a1 + 235) = v14;
      *(_BYTE *)(a1 + 236) = v13;
      *(_BYTE *)(a1 + 237) = v12;
      *(_BYTE *)(a1 + 238) = v11;
      *(_BYTE *)(a1 + 239) = v10;
      *(_BYTE *)(a1 + 240) = v9;
      *(_BYTE *)(a1 + 241) = v8;
      *(_BYTE *)(a1 + 242) = v7;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = 18;
    v19 = 10;
    v21 = InformationFile;
    v20 = 51;
LABEL_13:
    LOBYTE(v4) = 3;
    WPP_RECORDER_SF_sDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      12,
      v19,
      (__int64)WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
      v20,
      v21,
      v22);
  }
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x140022edc  push    rbp
0x140022ede  push    rbx
0x140022edf  push    rsi
0x140022ee0  push    rdi
0x140022ee1  push    r12
0x140022ee3  push    r13
0x140022ee5  push    r14
0x140022ee7  push    r15
0x140022ee9  lea     rbp, [rsp-8]
0x140022eee  sub     rsp, 108h
0x140022ef5  mov     rax, cs:__security_cookie
0x140022efc  xor     rax, rsp
0x140022eff  mov     [rbp+40h+var_50], rax
0x140022f03  mov     rdi, rcx
0x140022f06  mov     ebx, 68h ; 'h'
0x140022f0b  mov     r8d, ebx; Size
0x140022f0e  lea     rcx, [rbp+40h+FileInformation]; void *
0x140022f12  xor     edx, edx; Val
0x140022f14  call    memset
0x140022f19  mov     rdx, [rdi+68h]; FileObject
0x140022f1d  lea     r14d, [rbx-56h]
0x140022f21  mov     rcx, [rdi+48h]; Instance
0x140022f25  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140022f29  xor     esi, esi
0x140022f2b  xorps   xmm0, xmm0
0x140022f2e  xor     eax, eax
0x140022f30  mov     [rsp+140h+LengthReturned], rsi; LengthReturned
0x140022f35  mov     r9d, ebx; Length
0x140022f38  mov     [rsp+140h+var_D0], rax
0x140022f3d  movups  [rsp+140h+var_E0], xmm0
0x140022f42  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x140022f47  mov     [rsp+140h+var_E8], rsi
0x140022f4c  call    cs:__imp_FltQueryInformationFile
0x140022f53  nop     dword ptr [rax+rax+00h]
0x140022f58  mov     ebx, eax
0x140022f5a  mov     eax, 80000000h
0x140022f5f  lea     ecx, [rbx+rax]
0x140022f62  test    eax, ecx
0x140022f64  jz      loc_14002314B
0x140022f6a  mov     rdx, [rdi+68h]; FileObject
0x140022f6e  lea     r8, [rsp+140h+var_E8]; FileInformation
0x140022f73  mov     rcx, [rdi+48h]; Instance
0x140022f77  mov     r14d, 23h ; '#'
0x140022f7d  mov     [rsp+140h+LengthReturned], rsi; LengthReturned
0x140022f82  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x140022f87  lea     r9d, [r14-1Bh]; Length
0x140022f8b  call    cs:__imp_FltQueryInformationFile
0x140022f92  nop     dword ptr [rax+rax+00h]
0x140022f97  mov     ebx, eax
0x140022f99  test    eax, eax
0x140022f9b  js      loc_140023180
0x140022fa1  mov     rdx, [rdi+68h]; FileObject
0x140022fa5  lea     r8, [rsp+140h+var_E0]; FileInformation
0x140022faa  mov     rcx, [rdi+48h]; Instance
0x140022fae  mov     r14d, 3Bh ; ';'
0x140022fb4  mov     [rsp+140h+LengthReturned], rsi; LengthReturned
0x140022fb9  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x140022fbe  lea     r9d, [r14-23h]; Length
0x140022fc2  call    cs:__imp_FltQueryInformationFile
0x140022fc9  nop     dword ptr [rax+rax+00h]
0x140022fce  mov     ecx, 0C00000BBh
0x140022fd3  mov     ebx, eax
0x140022fd5  cmp     eax, ecx
0x140022fd7  jz      loc_1400231F5
0x140022fdd  test    eax, eax
0x140022fdf  js      loc_140023281
0x140022fe5  mov     al, byte ptr [rsp+140h+var_D0+7]
0x140022fe9  mov     r13b, byte ptr [rsp+140h+var_D0+2]
0x140022fee  mov     r12b, byte ptr [rsp+140h+var_D0+1]
0x140022ff3  mov     r15b, byte ptr [rsp+140h+var_D0]
0x140022ff8  mov     r14b, byte ptr [rsp+140h+var_E0+0Fh]
0x140022ffd  mov     sil, byte ptr [rsp+140h+var_E0+0Eh]
0x140023002  mov     r11b, byte ptr [rsp+140h+var_E0+0Dh]
0x140023007  mov     r10b, byte ptr [rsp+140h+var_E0+0Ch]
0x14002300c  mov     r9b, byte ptr [rsp+140h+var_E0+0Bh]
0x140023011  mov     r8b, byte ptr [rsp+140h+var_E0+0Ah]
0x140023016  mov     dl, byte ptr [rsp+140h+var_E0+9]
0x14002301a  mov     cl, byte ptr [rsp+140h+var_E0+8]
0x14002301e  mov     byte ptr [rsp+140h+var_EF+3], al
0x140023022  mov     al, byte ptr [rsp+140h+var_D0+6]
0x140023026  mov     byte ptr [rsp+140h+var_EF+2], al
0x14002302a  mov     al, byte ptr [rsp+140h+var_D0+5]
0x14002302e  mov     byte ptr [rsp+140h+var_EF+1], al
0x140023032  mov     al, byte ptr [rsp+140h+var_D0+4]
0x140023036  mov     byte ptr [rsp+140h+var_EF], al
0x14002303a  mov     al, byte ptr [rsp+140h+var_D0+3]
0x14002303e  mov     [rsp+140h+var_F0], al
0x140023042  mov     rax, [rbp+40h+var_98]
0x140023046  mov     [rdi+0C8h], rax
0x14002304d  mov     rax, [rbp+40h+var_A8]
0x140023051  mov     [rdi+0B8h], rax
0x140023058  mov     rax, [rbp+40h+FileInformation]
0x14002305c  mov     [rdi+0A0h], rax
0x140023063  mov     eax, [rbp+40h+var_78]
0x140023066  mov     [rdi+0D8h], eax
0x14002306c  mov     rax, [rbp+40h+var_90]
0x140023070  mov     [rdi+0C0h], rax
0x140023077  mov     eax, [rbp+40h+var_A0]
0x14002307a  mov     [rdi+0D0h], eax
0x140023080  mov     rax, [rbp+40h+var_B8]
0x140023084  mov     [rdi+0A8h], rax
0x14002308b  mov     rax, [rbp+40h+var_B0]
0x14002308f  mov     [rdi+0B0h], rax
0x140023096  mov     eax, dword ptr [rsp+140h+var_E8+4]
0x14002309a  mov     [rdi+0DCh], eax
0x1400230a0  mov     al, [rsp+140h+var_F0]
0x1400230a4  mov     [rdi+0F3h], al
0x1400230aa  mov     al, byte ptr [rsp+140h+var_EF]
0x1400230ae  mov     [rdi+0F4h], al
0x1400230b4  mov     al, byte ptr [rsp+140h+var_EF+1]
0x1400230b8  mov     [rdi+0F5h], al
0x1400230be  mov     al, byte ptr [rsp+140h+var_EF+2]
0x1400230c2  mov     [rdi+0F6h], al
0x1400230c8  mov     al, byte ptr [rsp+140h+var_EF+3]
0x1400230cc  mov     [rdi+0F7h], al
0x1400230d2  mov     rax, [rbp+40h+var_80]
0x1400230d6  mov     [rdi+0E0h], rax
0x1400230dd  mov     [rdi+0E8h], cl
0x1400230e3  mov     [rdi+0E9h], dl
0x1400230e9  mov     [rdi+0EAh], r8b
0x1400230f0  mov     [rdi+0EBh], r9b
0x1400230f7  mov     [rdi+0ECh], r10b
0x1400230fe  mov     [rdi+0EDh], r11b
0x140023105  mov     [rdi+0EEh], sil
0x14002310c  mov     [rdi+0EFh], r14b
0x140023113  mov     [rdi+0F0h], r15b
0x14002311a  mov     [rdi+0F1h], r12b
0x140023121  mov     [rdi+0F2h], r13b
0x140023128  mov     eax, ebx
0x14002312a  mov     rcx, [rbp+40h+var_50]
0x14002312e  xor     rcx, rsp; StackCookie
0x140023131  call    __security_check_cookie
0x140023136  add     rsp, 108h
0x14002313d  pop     r15
0x14002313f  pop     r14
0x140023141  pop     r13
0x140023143  pop     r12
0x140023145  pop     rdi
0x140023146  pop     rsi
0x140023147  pop     rbx
0x140023148  pop     rbp
0x140023149  retn
0x14002314b  cmp     ebx, 80000005h
0x140023151  jz      loc_140022F6A
0x140023157  lea     rax, WPP_RECORDER_INITIALIZED
0x14002315e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023165  jz      short loc_140023128
0x140023167  mov     dword ptr [rsp+140h+var_100], r14d
0x14002316c  mov     r9d, 0Ah
0x140023172  mov     dword ptr [rsp+140h+var_108], ebx
0x140023176  mov     dword ptr [rsp+140h+var_110], 133h
0x14002317e  jmp     short loc_1400231C0
0x140023180  lea     rax, WPP_RECORDER_INITIALIZED
0x140023187  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002318e  jz      short loc_140023128
0x140023190  mov     dword ptr [rsp+140h+var_100], r14d
0x140023195  mov     r9d, 0Bh
0x14002319b  mov     dword ptr [rsp+140h+var_108], ebx
0x14002319f  mov     dword ptr [rsp+140h+var_110], 13Fh
0x1400231a7  jmp     short loc_1400231C0
0x1400231a9  mov     dword ptr [rsp+140h+var_100], r14d
0x1400231ae  mov     r9d, 0Dh
0x1400231b4  mov     dword ptr [rsp+140h+var_108], ebx
0x1400231b8  mov     dword ptr [rsp+140h+var_110], 151h
0x1400231c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400231c7  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400231ce  mov     [rsp+140h+LengthReturned], rax
0x1400231d3  mov     r8d, 0Ch
0x1400231d9  lea     rax, WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids
0x1400231e0  mov     dl, 3
0x1400231e2  mov     qword ptr [rsp+140h+FileInformationClass], rax
0x1400231e7  mov     rcx, [rcx+40h]
0x1400231eb  call    WPP_RECORDER_SF_sDdd
0x1400231f0  jmp     loc_140023128
0x1400231f5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400231fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023203  jz      short loc_140023249
0x140023205  mov     dword ptr [rsp+140h+var_100], r14d
0x14002320a  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140023211  mov     dword ptr [rsp+140h+var_108], ecx
0x140023215  mov     r9d, 0Ch
0x14002321b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023222  mov     r8d, r9d
0x140023225  mov     dword ptr [rsp+140h+var_110], 14Ch
0x14002322d  mov     dl, 4
0x14002322f  mov     [rsp+140h+LengthReturned], rax
0x140023234  lea     rax, WPP_e12ce5656ffd33908c95ca7de20f6d85_Traceguids
0x14002323b  mov     qword ptr [rsp+140h+FileInformationClass], rax
0x140023240  mov     rcx, [rcx+40h]
0x140023244  call    WPP_RECORDER_SF_sDdd
0x140023249  mov     cl, 0FFh
0x14002324b  mov     dl, cl
0x14002324d  mov     [rsp+140h+var_F0], cl
0x140023251  mov     r8b, cl
0x140023254  mov     byte ptr [rsp+140h+var_EF], cl
0x140023258  mov     r9b, cl
0x14002325b  mov     byte ptr [rsp+140h+var_EF+1], cl
0x14002325f  mov     r10b, cl
0x140023262  mov     byte ptr [rsp+140h+var_EF+2], cl
0x140023266  mov     r11b, cl
0x140023269  mov     byte ptr [rsp+140h+var_EF+3], cl
0x14002326d  mov     sil, cl
0x140023270  mov     r14b, cl
0x140023273  mov     r15b, cl
0x140023276  mov     r12b, cl
0x140023279  mov     r13b, cl
0x14002327c  jmp     loc_140023042
0x140023281  lea     rax, WPP_RECORDER_INITIALIZED
0x140023288  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002328f  jz      loc_140023128
0x140023295  jmp     loc_1400231A9
```

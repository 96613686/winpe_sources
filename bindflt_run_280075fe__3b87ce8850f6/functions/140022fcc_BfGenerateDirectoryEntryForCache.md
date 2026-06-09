# BfGenerateDirectoryEntryForCache

- ea: `0x140022fcc`
- end: `0x14002338a`
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
- `0x140022fcc`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x14002303c`
- `FLTMGR!FltQueryInformationFile` at `0x14002307b`
- `FLTMGR!FltQueryInformationFile` at `0x1400230b2`
- `FLTMGR!FltQueryInformationFile` at `0x14002303c`
- `FLTMGR!FltQueryInformationFile` at `0x14002307b`
- `FLTMGR!FltQueryInformationFile` at `0x1400230b2`

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
        v20 = 61;
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
            (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\dirctrl.c",
            74,
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
          v20 = 79;
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
    v20 = 49;
LABEL_13:
    LOBYTE(v4) = 3;
    WPP_RECORDER_SF_sDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      12,
      v19,
      (__int64)WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids,
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
0x140022fcc  push    rbp
0x140022fce  push    rbx
0x140022fcf  push    rsi
0x140022fd0  push    rdi
0x140022fd1  push    r12
0x140022fd3  push    r13
0x140022fd5  push    r14
0x140022fd7  push    r15
0x140022fd9  lea     rbp, [rsp-8]
0x140022fde  sub     rsp, 108h
0x140022fe5  mov     rax, cs:__security_cookie
0x140022fec  xor     rax, rsp
0x140022fef  mov     [rbp+40h+var_50], rax
0x140022ff3  mov     rdi, rcx
0x140022ff6  mov     ebx, 68h ; 'h'
0x140022ffb  mov     r8d, ebx; Size
0x140022ffe  lea     rcx, [rbp+40h+FileInformation]; void *
0x140023002  xor     edx, edx; Val
0x140023004  call    memset
0x140023009  mov     rdx, [rdi+68h]; FileObject
0x14002300d  lea     r14d, [rbx-56h]
0x140023011  mov     rcx, [rdi+48h]; Instance
0x140023015  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140023019  xor     esi, esi
0x14002301b  xorps   xmm0, xmm0
0x14002301e  xor     eax, eax
0x140023020  mov     [rsp+140h+LengthReturned], rsi; LengthReturned
0x140023025  mov     r9d, ebx; Length
0x140023028  mov     [rsp+140h+var_D0], rax
0x14002302d  movups  [rsp+140h+var_E0], xmm0
0x140023032  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x140023037  mov     [rsp+140h+var_E8], rsi
0x14002303c  call    cs:__imp_FltQueryInformationFile
0x140023043  nop     dword ptr [rax+rax+00h]
0x140023048  mov     ebx, eax
0x14002304a  mov     eax, 80000000h
0x14002304f  lea     ecx, [rbx+rax]
0x140023052  test    eax, ecx
0x140023054  jz      loc_14002323B
0x14002305a  mov     rdx, [rdi+68h]; FileObject
0x14002305e  lea     r8, [rsp+140h+var_E8]; FileInformation
0x140023063  mov     rcx, [rdi+48h]; Instance
0x140023067  mov     r14d, 23h ; '#'
0x14002306d  mov     [rsp+140h+LengthReturned], rsi; LengthReturned
0x140023072  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x140023077  lea     r9d, [r14-1Bh]; Length
0x14002307b  call    cs:__imp_FltQueryInformationFile
0x140023082  nop     dword ptr [rax+rax+00h]
0x140023087  mov     ebx, eax
0x140023089  test    eax, eax
0x14002308b  js      loc_140023270
0x140023091  mov     rdx, [rdi+68h]; FileObject
0x140023095  lea     r8, [rsp+140h+var_E0]; FileInformation
0x14002309a  mov     rcx, [rdi+48h]; Instance
0x14002309e  mov     r14d, 3Bh ; ';'
0x1400230a4  mov     [rsp+140h+LengthReturned], rsi; LengthReturned
0x1400230a9  mov     [rsp+140h+FileInformationClass], r14d; FileInformationClass
0x1400230ae  lea     r9d, [r14-23h]; Length
0x1400230b2  call    cs:__imp_FltQueryInformationFile
0x1400230b9  nop     dword ptr [rax+rax+00h]
0x1400230be  mov     ecx, 0C00000BBh
0x1400230c3  mov     ebx, eax
0x1400230c5  cmp     eax, ecx
0x1400230c7  jz      loc_1400232E5
0x1400230cd  test    eax, eax
0x1400230cf  js      loc_140023371
0x1400230d5  mov     al, byte ptr [rsp+140h+var_D0+7]
0x1400230d9  mov     r13b, byte ptr [rsp+140h+var_D0+2]
0x1400230de  mov     r12b, byte ptr [rsp+140h+var_D0+1]
0x1400230e3  mov     r15b, byte ptr [rsp+140h+var_D0]
0x1400230e8  mov     r14b, byte ptr [rsp+140h+var_E0+0Fh]
0x1400230ed  mov     sil, byte ptr [rsp+140h+var_E0+0Eh]
0x1400230f2  mov     r11b, byte ptr [rsp+140h+var_E0+0Dh]
0x1400230f7  mov     r10b, byte ptr [rsp+140h+var_E0+0Ch]
0x1400230fc  mov     r9b, byte ptr [rsp+140h+var_E0+0Bh]
0x140023101  mov     r8b, byte ptr [rsp+140h+var_E0+0Ah]
0x140023106  mov     dl, byte ptr [rsp+140h+var_E0+9]
0x14002310a  mov     cl, byte ptr [rsp+140h+var_E0+8]
0x14002310e  mov     byte ptr [rsp+140h+var_EF+3], al
0x140023112  mov     al, byte ptr [rsp+140h+var_D0+6]
0x140023116  mov     byte ptr [rsp+140h+var_EF+2], al
0x14002311a  mov     al, byte ptr [rsp+140h+var_D0+5]
0x14002311e  mov     byte ptr [rsp+140h+var_EF+1], al
0x140023122  mov     al, byte ptr [rsp+140h+var_D0+4]
0x140023126  mov     byte ptr [rsp+140h+var_EF], al
0x14002312a  mov     al, byte ptr [rsp+140h+var_D0+3]
0x14002312e  mov     [rsp+140h+var_F0], al
0x140023132  mov     rax, [rbp+40h+var_98]
0x140023136  mov     [rdi+0C8h], rax
0x14002313d  mov     rax, [rbp+40h+var_A8]
0x140023141  mov     [rdi+0B8h], rax
0x140023148  mov     rax, [rbp+40h+FileInformation]
0x14002314c  mov     [rdi+0A0h], rax
0x140023153  mov     eax, [rbp+40h+var_78]
0x140023156  mov     [rdi+0D8h], eax
0x14002315c  mov     rax, [rbp+40h+var_90]
0x140023160  mov     [rdi+0C0h], rax
0x140023167  mov     eax, [rbp+40h+var_A0]
0x14002316a  mov     [rdi+0D0h], eax
0x140023170  mov     rax, [rbp+40h+var_B8]
0x140023174  mov     [rdi+0A8h], rax
0x14002317b  mov     rax, [rbp+40h+var_B0]
0x14002317f  mov     [rdi+0B0h], rax
0x140023186  mov     eax, dword ptr [rsp+140h+var_E8+4]
0x14002318a  mov     [rdi+0DCh], eax
0x140023190  mov     al, [rsp+140h+var_F0]
0x140023194  mov     [rdi+0F3h], al
0x14002319a  mov     al, byte ptr [rsp+140h+var_EF]
0x14002319e  mov     [rdi+0F4h], al
0x1400231a4  mov     al, byte ptr [rsp+140h+var_EF+1]
0x1400231a8  mov     [rdi+0F5h], al
0x1400231ae  mov     al, byte ptr [rsp+140h+var_EF+2]
0x1400231b2  mov     [rdi+0F6h], al
0x1400231b8  mov     al, byte ptr [rsp+140h+var_EF+3]
0x1400231bc  mov     [rdi+0F7h], al
0x1400231c2  mov     rax, [rbp+40h+var_80]
0x1400231c6  mov     [rdi+0E0h], rax
0x1400231cd  mov     [rdi+0E8h], cl
0x1400231d3  mov     [rdi+0E9h], dl
0x1400231d9  mov     [rdi+0EAh], r8b
0x1400231e0  mov     [rdi+0EBh], r9b
0x1400231e7  mov     [rdi+0ECh], r10b
0x1400231ee  mov     [rdi+0EDh], r11b
0x1400231f5  mov     [rdi+0EEh], sil
0x1400231fc  mov     [rdi+0EFh], r14b
0x140023203  mov     [rdi+0F0h], r15b
0x14002320a  mov     [rdi+0F1h], r12b
0x140023211  mov     [rdi+0F2h], r13b
0x140023218  mov     eax, ebx
0x14002321a  mov     rcx, [rbp+40h+var_50]
0x14002321e  xor     rcx, rsp; StackCookie
0x140023221  call    __security_check_cookie
0x140023226  add     rsp, 108h
0x14002322d  pop     r15
0x14002322f  pop     r14
0x140023231  pop     r13
0x140023233  pop     r12
0x140023235  pop     rdi
0x140023236  pop     rsi
0x140023237  pop     rbx
0x140023238  pop     rbp
0x140023239  retn
0x14002323b  cmp     ebx, 80000005h
0x140023241  jz      loc_14002305A
0x140023247  lea     rax, WPP_RECORDER_INITIALIZED
0x14002324e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140023255  jz      short loc_140023218
0x140023257  mov     dword ptr [rsp+140h+var_100], r14d
0x14002325c  mov     r9d, 0Ah
0x140023262  mov     dword ptr [rsp+140h+var_108], ebx
0x140023266  mov     dword ptr [rsp+140h+var_110], 131h
0x14002326e  jmp     short loc_1400232B0
0x140023270  lea     rax, WPP_RECORDER_INITIALIZED
0x140023277  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002327e  jz      short loc_140023218
0x140023280  mov     dword ptr [rsp+140h+var_100], r14d
0x140023285  mov     r9d, 0Bh
0x14002328b  mov     dword ptr [rsp+140h+var_108], ebx
0x14002328f  mov     dword ptr [rsp+140h+var_110], 13Dh
0x140023297  jmp     short loc_1400232B0
0x140023299  mov     dword ptr [rsp+140h+var_100], r14d
0x14002329e  mov     r9d, 0Dh
0x1400232a4  mov     dword ptr [rsp+140h+var_108], ebx
0x1400232a8  mov     dword ptr [rsp+140h+var_110], 14Fh
0x1400232b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232b7  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400232be  mov     [rsp+140h+LengthReturned], rax
0x1400232c3  mov     r8d, 0Ch
0x1400232c9  lea     rax, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x1400232d0  mov     dl, 3
0x1400232d2  mov     qword ptr [rsp+140h+FileInformationClass], rax
0x1400232d7  mov     rcx, [rcx+40h]
0x1400232db  call    WPP_RECORDER_SF_sDdd
0x1400232e0  jmp     loc_140023218
0x1400232e5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400232ec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400232f3  jz      short loc_140023339
0x1400232f5  mov     dword ptr [rsp+140h+var_100], r14d
0x1400232fa  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140023301  mov     dword ptr [rsp+140h+var_108], ecx
0x140023305  mov     r9d, 0Ch
0x14002330b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023312  mov     r8d, r9d
0x140023315  mov     dword ptr [rsp+140h+var_110], 14Ah
0x14002331d  mov     dl, 4
0x14002331f  mov     [rsp+140h+LengthReturned], rax
0x140023324  lea     rax, WPP_7c51d40b00ec3a3e74a53df28c1d8c0d_Traceguids
0x14002332b  mov     qword ptr [rsp+140h+FileInformationClass], rax
0x140023330  mov     rcx, [rcx+40h]
0x140023334  call    WPP_RECORDER_SF_sDdd
0x140023339  mov     cl, 0FFh
0x14002333b  mov     dl, cl
0x14002333d  mov     [rsp+140h+var_F0], cl
0x140023341  mov     r8b, cl
0x140023344  mov     byte ptr [rsp+140h+var_EF], cl
0x140023348  mov     r9b, cl
0x14002334b  mov     byte ptr [rsp+140h+var_EF+1], cl
0x14002334f  mov     r10b, cl
0x140023352  mov     byte ptr [rsp+140h+var_EF+2], cl
0x140023356  mov     r11b, cl
0x140023359  mov     byte ptr [rsp+140h+var_EF+3], cl
0x14002335d  mov     sil, cl
0x140023360  mov     r14b, cl
0x140023363  mov     r15b, cl
0x140023366  mov     r12b, cl
0x140023369  mov     r13b, cl
0x14002336c  jmp     loc_140023132
0x140023371  lea     rax, WPP_RECORDER_INITIALIZED
0x140023378  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002337f  jz      loc_140023218
0x140023385  jmp     loc_140023299
```

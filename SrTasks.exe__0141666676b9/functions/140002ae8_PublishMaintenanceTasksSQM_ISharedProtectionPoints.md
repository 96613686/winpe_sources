# PublishMaintenanceTasksSQM(ISharedProtectionPoints *)

- ea: `0x140002ae8`
- end: `0x140002e16`
- name: `?PublishMaintenanceTasksSQM@@YAJPEAUISharedProtectionPoints@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(struct ISharedProtectionPoints *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140004a70`

## callees

- `0x140001b3c`
- `0x140001dec`
- `0x1400020c4`
- `0x1400022c0`
- `0x140002484`
- `0x140002670`
- `0x140002ae8`
- `0x140002e1c`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140010980`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x140002de5`
- `ntdll!WinSqmAddToStreamEx` at `0x140002de5`

## string_xrefs

- `0x140002b46`: `PublishMaintenanceTasksSQM`

## pseudocode

```c
__int64 __fastcall PublishMaintenanceTasksSQM(struct ISharedProtectionPoints *a1)
{
  __int16 v2; // ax
  int MainenanceTaskFrequency; // ebx
  unsigned __int8 v5; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v6; // [rsp+31h] [rbp-CFh] BYREF
  int v7; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v8; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v9; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v10; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v11; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v12; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v13; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v14; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v15; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v16; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v17; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v18; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v19; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v20; // [rsp+68h] [rbp-98h] BYREF
  int v21; // [rsp+70h] [rbp-90h] BYREF
  __int16 v22; // [rsp+74h] [rbp-8Ch]
  __int16 v23; // [rsp+76h] [rbp-8Ah]
  int v24; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v25[63]; // [rsp+B4h] [rbp-4Ch] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_cc2da48973373651002ff2feee037f2e_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "PublishMaintenanceTasksSQM", 466, 1);
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v5 = 0;
  v19 = 0;
  v6 = 0;
  v20 = 0;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v2 = 486;
  if ( a1 )
  {
    v21 = 0;
    v22 = 486;
    MainenanceTaskFrequency = CheckSREnabled(a1, &v7, &v8);
    v21 = MainenanceTaskFrequency;
    v2 = 491;
    if ( MainenanceTaskFrequency >= 0 )
    {
      v22 = 491;
      MainenanceTaskFrequency = GetMainenanceTaskFrequency(&v9);
      v21 = MainenanceTaskFrequency;
      v2 = 493;
      if ( MainenanceTaskFrequency >= 0 )
      {
        v22 = 493;
        MainenanceTaskFrequency = GetSnapshotsCount(&v10, &v11);
        v21 = MainenanceTaskFrequency;
        v2 = 495;
        if ( MainenanceTaskFrequency >= 0 )
        {
          v22 = 495;
          MainenanceTaskFrequency = GetRestorePointsCount(&v12, &v13, &v14);
          v21 = MainenanceTaskFrequency;
          v2 = 498;
          if ( MainenanceTaskFrequency >= 0 )
          {
            v22 = 498;
            MainenanceTaskFrequency = GetBootVolumeSizeStats(&v15, &v16, &v17, &v18);
            v21 = MainenanceTaskFrequency;
            v2 = 501;
            if ( MainenanceTaskFrequency >= 0 )
            {
              v22 = 501;
              MainenanceTaskFrequency = GetRegistryKeySettings((bool *)&v5, &v19, (bool *)&v6, &v20);
              v21 = MainenanceTaskFrequency;
              v2 = 504;
              if ( MainenanceTaskFrequency >= 0 )
              {
                v22 = 504;
                v25[1] = v7;
                v25[5] = v8;
                v25[9] = v9;
                v25[13] = v10;
                v25[17] = v11;
                v25[21] = v12;
                v25[25] = v13;
                v25[29] = v14;
                v25[33] = v15;
                v25[37] = v16;
                v25[41] = v17;
                v25[45] = v18;
                v25[49] = v5;
                v25[53] = v19;
                v25[57] = v6;
                v25[61] = v20;
                v24 = 16;
                v25[0] = 1;
                v25[3] = 16;
                v25[4] = 1;
                v25[7] = 16;
                v25[8] = 1;
                v25[11] = 16;
                v25[12] = 1;
                v25[15] = 16;
                v25[16] = 1;
                v25[19] = 16;
                v25[20] = 1;
                v25[23] = 16;
                v25[24] = 1;
                v25[27] = 16;
                v25[28] = 1;
                v25[31] = 16;
                v25[32] = 1;
                v25[35] = 16;
                v25[36] = 1;
                v25[39] = 16;
                v25[40] = 1;
                v25[43] = 16;
                v25[44] = 1;
                v25[47] = 16;
                v25[48] = 1;
                v25[51] = 16;
                v25[52] = 1;
                v25[55] = 16;
                v25[56] = 1;
                v25[59] = 16;
                v25[60] = 1;
                WinSqmAddToStreamEx(0, 8494, 16, &v24, 0);
                MainenanceTaskFrequency = v21;
                goto LABEL_14;
              }
            }
          }
        }
      }
    }
  }
  else
  {
    MainenanceTaskFrequency = -2147024809;
    v21 = -2147024809;
  }
  v23 = v2;
LABEL_14:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return (unsigned int)MainenanceTaskFrequency;
}

```

## disassembly

```asm
0x140002ae8  push    rbp
0x140002aea  push    rbx
0x140002aeb  push    rsi
0x140002aec  push    rdi
0x140002aed  lea     rbp, [rsp-0C8h]
0x140002af5  sub     rsp, 1C8h
0x140002afc  mov     rax, cs:__security_cookie
0x140002b03  xor     rax, rsp
0x140002b06  mov     [rbp+0E0h+var_30], rax
0x140002b0d  mov     rbx, rcx
0x140002b10  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b17  lea     rax, WPP_GLOBAL_Control
0x140002b1e  cmp     rcx, rax
0x140002b21  jz      short loc_140002B41
0x140002b23  test    dword ptr [rcx+1Ch], 20000000h
0x140002b2a  jz      short loc_140002B41
0x140002b2c  mov     rcx, [rcx+10h]
0x140002b30  lea     r8, WPP_cc2da48973373651002ff2feee037f2e_Traceguids
0x140002b37  mov     edx, 1Dh
0x140002b3c  call    WPP_SF_
0x140002b41  mov     esi, 1
0x140002b46  lea     rdx, aPublishmainten; "PublishMaintenanceTasksSQM"
0x140002b4d  mov     r9d, esi; unsigned __int16
0x140002b50  lea     rcx, [rsp+1E0h+var_170]; this
0x140002b55  mov     r8d, 1D2h; unsigned __int16
0x140002b5b  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140002b60  xor     edi, edi
0x140002b62  lea     rcx, [rbp+0E0h+var_12C]; void *
0x140002b66  xor     edx, edx; Val
0x140002b68  mov     [rsp+1E0h+var_1AC], edi
0x140002b6c  mov     r8d, 0FCh; Size
0x140002b72  mov     [rsp+1E0h+var_1A8], edi
0x140002b76  mov     [rsp+1E0h+var_1A4], edi
0x140002b7a  mov     [rsp+1E0h+var_1A0], edi
0x140002b7e  mov     [rsp+1E0h+var_19C], edi
0x140002b82  mov     [rsp+1E0h+var_198], edi
0x140002b86  mov     [rsp+1E0h+var_194], edi
0x140002b8a  mov     [rsp+1E0h+var_190], edi
0x140002b8e  mov     [rsp+1E0h+var_18C], edi
0x140002b92  mov     [rsp+1E0h+var_188], edi
0x140002b96  mov     [rsp+1E0h+var_184], edi
0x140002b9a  mov     [rsp+1E0h+var_180], edi
0x140002b9e  mov     [rsp+1E0h+var_1B0], dil
0x140002ba3  mov     [rsp+1E0h+var_17C], edi
0x140002ba7  mov     [rsp+1E0h+var_1AF], dil
0x140002bac  mov     [rsp+1E0h+var_178], edi
0x140002bb0  mov     [rbp+0E0h+var_130], edi
0x140002bb3  call    memset_0
0x140002bb8  mov     eax, 1E6h
0x140002bbd  test    rbx, rbx
0x140002bc0  jnz     short loc_140002BD5
0x140002bc2  mov     ebx, 80070057h
0x140002bc7  mov     [rsp+1E0h+var_170], ebx
0x140002bcb  mov     [rsp+1E0h+var_16A], ax
0x140002bd0  jmp     loc_140002DEF
0x140002bd5  lea     r8, [rsp+1E0h+var_1A8]; unsigned int *
0x140002bda  mov     [rsp+1E0h+var_170], edi
0x140002bde  lea     rdx, [rsp+1E0h+var_1AC]; int *
0x140002be3  mov     [rsp+1E0h+var_16C], ax
0x140002be8  mov     rcx, rbx; struct ISharedProtectionPoints *
0x140002beb  call    ?CheckSREnabled@@YAJPEAUISharedProtectionPoints@@PEAHPEAK@Z; CheckSREnabled(ISharedProtectionPoints *,int *,ulong *)
0x140002bf0  mov     ebx, eax
0x140002bf2  mov     [rsp+1E0h+var_170], eax
0x140002bf6  test    eax, eax
0x140002bf8  mov     eax, 1EBh
0x140002bfd  js      short loc_140002BCB
0x140002bff  lea     rcx, [rsp+1E0h+var_1A4]; unsigned int *
0x140002c04  mov     [rsp+1E0h+var_16C], ax
0x140002c09  call    ?GetMainenanceTaskFrequency@@YAJPEAK@Z; GetMainenanceTaskFrequency(ulong *)
0x140002c0e  mov     ebx, eax
0x140002c10  mov     [rsp+1E0h+var_170], eax
0x140002c14  test    eax, eax
0x140002c16  mov     eax, 1EDh
0x140002c1b  js      short loc_140002BCB
0x140002c1d  lea     rdx, [rsp+1E0h+var_19C]; unsigned int *
0x140002c22  mov     [rsp+1E0h+var_16C], ax
0x140002c27  lea     rcx, [rsp+1E0h+var_1A0]; unsigned int *
0x140002c2c  call    ?GetSnapshotsCount@@YAJPEAK0@Z; GetSnapshotsCount(ulong *,ulong *)
0x140002c31  mov     ebx, eax
0x140002c33  mov     [rsp+1E0h+var_170], eax
0x140002c37  test    eax, eax
0x140002c39  mov     eax, 1EFh
0x140002c3e  js      short loc_140002BCB
0x140002c40  lea     r8, [rsp+1E0h+var_190]; unsigned int *
0x140002c45  mov     [rsp+1E0h+var_16C], ax
0x140002c4a  lea     rdx, [rsp+1E0h+var_194]; unsigned int *
0x140002c4f  lea     rcx, [rsp+1E0h+var_198]; unsigned int *
0x140002c54  call    ?GetRestorePointsCount@@YAJPEAK00@Z; GetRestorePointsCount(ulong *,ulong *,ulong *)
0x140002c59  mov     ebx, eax
0x140002c5b  mov     [rsp+1E0h+var_170], eax
0x140002c5f  test    eax, eax
0x140002c61  mov     eax, 1F2h
0x140002c66  js      loc_140002BCB
0x140002c6c  lea     r9, [rsp+1E0h+var_180]; unsigned int *
0x140002c71  mov     [rsp+1E0h+var_16C], ax
0x140002c76  lea     r8, [rsp+1E0h+var_184]; unsigned int *
0x140002c7b  lea     rdx, [rsp+1E0h+var_188]; unsigned int *
0x140002c80  lea     rcx, [rsp+1E0h+var_18C]; unsigned int *
0x140002c85  call    ?GetBootVolumeSizeStats@@YAJPEAK000@Z; GetBootVolumeSizeStats(ulong *,ulong *,ulong *,ulong *)
0x140002c8a  mov     ebx, eax
0x140002c8c  mov     [rsp+1E0h+var_170], eax
0x140002c90  test    eax, eax
0x140002c92  mov     eax, 1F5h
0x140002c97  js      loc_140002BCB
0x140002c9d  lea     r9, [rsp+1E0h+var_178]; unsigned int *
0x140002ca2  mov     [rsp+1E0h+var_16C], ax
0x140002ca7  lea     r8, [rsp+1E0h+var_1AF]; unsigned __int8 *
0x140002cac  lea     rdx, [rsp+1E0h+var_17C]; unsigned int *
0x140002cb1  lea     rcx, [rsp+1E0h+var_1B0]; unsigned __int8 *
0x140002cb6  call    ?GetRegistryKeySettings@@YAJPEAEPEAK01@Z; GetRegistryKeySettings(uchar *,ulong *,uchar *,ulong *)
0x140002cbb  mov     ebx, eax
0x140002cbd  mov     [rsp+1E0h+var_170], eax
0x140002cc1  test    eax, eax
0x140002cc3  mov     eax, 1F8h
0x140002cc8  js      loc_140002BCB
0x140002cce  mov     [rsp+1E0h+var_16C], ax
0x140002cd3  lea     r9, [rbp+0E0h+var_130]
0x140002cd7  mov     eax, [rsp+1E0h+var_1AC]
0x140002cdb  mov     r8d, 10h
0x140002ce1  mov     [rbp+0E0h+var_128], eax
0x140002ce4  mov     edx, 212Eh
0x140002ce9  mov     eax, [rsp+1E0h+var_1A8]
0x140002ced  xor     ecx, ecx
0x140002cef  mov     [rbp+0E0h+var_118], eax
0x140002cf2  mov     eax, [rsp+1E0h+var_1A4]
0x140002cf6  mov     [rbp+0E0h+var_108], eax
0x140002cf9  mov     eax, [rsp+1E0h+var_1A0]
0x140002cfd  mov     [rbp+0E0h+var_F8], eax
0x140002d00  mov     eax, [rsp+1E0h+var_19C]
0x140002d04  mov     [rbp+0E0h+var_E8], eax
0x140002d07  mov     eax, [rsp+1E0h+var_198]
0x140002d0b  mov     [rbp+0E0h+var_D8], eax
0x140002d0e  mov     eax, [rsp+1E0h+var_194]
0x140002d12  mov     [rbp+0E0h+var_C8], eax
0x140002d15  mov     eax, [rsp+1E0h+var_190]
0x140002d19  mov     [rbp+0E0h+var_B8], eax
0x140002d1c  mov     eax, [rsp+1E0h+var_18C]
0x140002d20  mov     [rbp+0E0h+var_A8], eax
0x140002d23  mov     eax, [rsp+1E0h+var_188]
0x140002d27  mov     [rbp+0E0h+var_98], eax
0x140002d2a  mov     eax, [rsp+1E0h+var_184]
0x140002d2e  mov     [rbp+0E0h+var_88], eax
0x140002d31  mov     eax, [rsp+1E0h+var_180]
0x140002d35  mov     [rbp+0E0h+var_78], eax
0x140002d38  movzx   eax, [rsp+1E0h+var_1B0]
0x140002d3d  mov     [rbp+0E0h+var_68], eax
0x140002d40  mov     eax, [rsp+1E0h+var_17C]
0x140002d44  mov     [rbp+0E0h+var_58], eax
0x140002d4a  movzx   eax, [rsp+1E0h+var_1AF]
0x140002d4f  mov     [rbp+0E0h+var_48], eax
0x140002d55  mov     eax, [rsp+1E0h+var_178]
0x140002d59  mov     [rbp+0E0h+var_38], eax
0x140002d5f  mov     [rbp+0E0h+var_130], r8d
0x140002d63  mov     [rbp+0E0h+var_12C], esi
0x140002d66  mov     [rbp+0E0h+var_120], r8d
0x140002d6a  mov     [rbp+0E0h+var_11C], esi
0x140002d6d  mov     [rbp+0E0h+var_110], r8d
0x140002d71  mov     [rbp+0E0h+var_10C], esi
0x140002d74  mov     [rbp+0E0h+var_100], r8d
0x140002d78  mov     [rbp+0E0h+var_FC], esi
0x140002d7b  mov     [rbp+0E0h+var_F0], r8d
0x140002d7f  mov     [rbp+0E0h+var_EC], esi
0x140002d82  mov     [rbp+0E0h+var_E0], r8d
0x140002d86  mov     [rbp+0E0h+var_DC], esi
0x140002d89  mov     [rbp+0E0h+var_D0], r8d
0x140002d8d  mov     [rbp+0E0h+var_CC], esi
0x140002d90  mov     [rbp+0E0h+var_C0], r8d
0x140002d94  mov     [rbp+0E0h+var_BC], esi
0x140002d97  mov     [rbp+0E0h+var_B0], r8d
0x140002d9b  mov     [rbp+0E0h+var_AC], esi
0x140002d9e  mov     [rbp+0E0h+var_A0], r8d
0x140002da2  mov     [rbp+0E0h+var_9C], esi
0x140002da5  mov     [rbp+0E0h+var_90], r8d
0x140002da9  mov     [rbp+0E0h+var_8C], esi
0x140002dac  mov     [rbp+0E0h+var_80], r8d
0x140002db0  mov     [rbp+0E0h+var_7C], esi
0x140002db3  mov     [rbp+0E0h+var_70], r8d
0x140002db7  mov     [rbp+0E0h+var_6C], esi
0x140002dba  mov     [rbp+0E0h+var_60], r8d
0x140002dc1  mov     [rbp+0E0h+var_5C], esi
0x140002dc7  mov     [rbp+0E0h+var_50], r8d
0x140002dce  mov     [rbp+0E0h+var_4C], esi
0x140002dd4  mov     [rbp+0E0h+var_40], r8d
0x140002ddb  mov     [rbp+0E0h+var_3C], esi
0x140002de1  mov     [rsp+1E0h+var_1C0], edi
0x140002de5  call    cs:__imp_WinSqmAddToStreamEx
0x140002deb  mov     ebx, [rsp+1E0h+var_170]
0x140002def  lea     rcx, [rsp+1E0h+var_170]; this
0x140002df4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140002df9  mov     eax, ebx
0x140002dfb  mov     rcx, [rbp+0E0h+var_30]
0x140002e02  xor     rcx, rsp; StackCookie
0x140002e05  call    __security_check_cookie
0x140002e0a  add     rsp, 1C8h
0x140002e11  pop     rdi
0x140002e12  pop     rsi
0x140002e13  pop     rbx
0x140002e14  pop     rbp
0x140002e15  retn
```

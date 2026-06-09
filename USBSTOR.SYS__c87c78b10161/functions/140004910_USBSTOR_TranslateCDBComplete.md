# USBSTOR_TranslateCDBComplete

- ea: `0x140004910`
- end: `0x140004ebb`
- name: `USBSTOR_TranslateCDBComplete`
- size: `1451`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `11`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001de0`
- `0x1400023b0`
- `0x140003e10`
- `0x1400094b0`
- `0x140009860`
- `0x140009cb0`
- `0x140009f90`
- `0x14000c120`
- `0x14000f640`
- `0x14000fafc`
- `0x1400124f0`

## callees

- `0x140003630`
- `0x140004910`
- `0x140005d80`
- `0x14000cba8`
- `0x14000e3a4`
- `0x14000e8bc`
- `0x1400105e8`
- `0x1400114a4`
- `0x1400123b4`
- `0x14001288c`
- `0x140013950`
- `0x140013a40`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x14000495c`
- `ntoskrnl!KeCancelTimer` at `0x14000495c`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140004e65`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140004e65`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004bfa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004c71`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004bfa`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140004c71`
- `ntoskrnl!RtlCompareMemory` at `0x140004ade`
- `ntoskrnl!RtlCompareMemory` at `0x140004ade`
- `HAL!KeQueryPerformanceCounter` at `0x140004df1`
- `HAL!KeQueryPerformanceCounter` at `0x140004df1`

## pseudocode

```c
__int64 __fastcall USBSTOR_TranslateCDBComplete(_QWORD *Object, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v7; // r12
  int v8; // ebp
  char v9; // al
  _OWORD *v10; // r15
  __int64 v11; // rcx
  int v12; // eax
  int v14; // eax
  __int64 v15; // rcx
  PVOID v16; // r9
  unsigned int v17; // ecx
  int v18; // eax
  __int64 v19; // rcx
  _BYTE *v20; // rcx
  char v21; // al
  LARGE_INTEGER v22; // rax
  unsigned __int64 v23; // rdi
  LARGE_INTEGER v24; // r8
  unsigned __int64 v25; // r9
  int v26; // ecx
  int v27; // r9d
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-A8h]
  ULONG Priority; // [rsp+28h] [rbp-A0h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+70h] [rbp-58h] BYREF
  __int128 v31; // [rsp+78h] [rbp-50h] BYREF

  v3 = Object[8];
  v7 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 16LL);
  KeCancelTimer((PKTIMER)(v3 + 192));
  v8 = -1073741632;
  if ( *(_BYTE *)(*(_QWORD *)(v3 + 64) + 6LL) != 6 )
  {
    v9 = *(_BYTE *)(a3 + 72);
    v10 = (_OWORD *)(a3 + 72);
    if ( v9 == *(_BYTE *)(v3 + 1176) )
      goto LABEL_3;
    if ( v9 == 90 )
    {
      v18 = *(_BYTE *)(a3 + 3) & 0x3F;
      if ( (v18 == 1 || v18 == 18) && *(_DWORD *)(a3 + 16) >= 8u )
      {
        v19 = *(_QWORD *)(a2 + 8);
        if ( v19 )
        {
          if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
            v20 = *(_BYTE **)(v19 + 24);
          else
            v20 = MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000010u);
          if ( !v20 )
          {
            *(_BYTE *)(a3 + 3) = 4;
            goto LABEL_53;
          }
        }
        else
        {
          v20 = *(_BYTE **)(a3 + 24);
        }
        *v20 = v20[1];
        v20[1] = v20[2];
        v20[2] = v20[3];
        v20[3] = v20[7];
        memmove(v20 + 4, v20 + 8, *(unsigned int *)(a3 + 16) - 8LL);
        *(_DWORD *)(a3 + 16) -= 4;
        v21 = 18;
        if ( *(char *)(a3 + 3) < 0 )
          v21 = -110;
        *(_BYTE *)(a3 + 3) = v21;
      }
    }
LABEL_53:
    *v10 = *(_OWORD *)(v3 + 1176);
    goto LABEL_3;
  }
  if ( (*(_BYTE *)(a3 + 3) & 0x3F) != 1 )
  {
    switch ( *(_BYTE *)(a3 + 3) & 0x3F )
    {
      case 8:
      case 0x11:
      case 0x20:
      case 0x21:
        v14 = -1073741632;
        goto LABEL_18;
      case 9:
      case 0xB:
      case 0xE:
        v14 = -1073741643;
        goto LABEL_18;
      case 0xA:
        v14 = -1073741667;
        goto LABEL_18;
      case 0x12:
        v10 = (_OWORD *)(a3 + 72);
        *(_DWORD *)(a2 + 48) = -2147483643;
        goto LABEL_3;
      case 0x15:
      case 0x22:
        v14 = -1073741808;
        goto LABEL_18;
      default:
        v14 = -1073741435;
LABEL_18:
        *(_DWORD *)(a2 + 48) = v14;
        break;
    }
  }
  v10 = (_OWORD *)(a3 + 72);
LABEL_3:
  v11 = *(unsigned __int8 *)(a3 + 3);
  if ( (v11 & 0x3F) != 1 && (*(_DWORD *)(a3 + 12) & 0x100) == 0 )
  {
    LOBYTE(v11) = v11 | 0x40;
    *(_BYTE *)(a3 + 3) = v11;
    if ( v7 )
      UsbQueueFreeze(v7 + 368);
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x1000000) != 0 )
    USBSTOR_SetModeSenseDataProtect(v11, a2, a3);
  v12 = *(_BYTE *)(a3 + 3) & 0x3F;
  if ( (v12 == 1 || v12 == 18)
    && *(_BYTE *)(a3 + 72) == 18
    && (*(_BYTE *)(a3 + 73) & ((*(_DWORD *)(v3 + 132) & 0x100) == 0)) != 0 )
  {
    v15 = *(_QWORD *)(a2 + 8);
    if ( v15 )
      v16 = (*(_BYTE *)(v15 + 10) & 5) != 0
          ? *(PVOID *)(v15 + 24)
          : MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u);
    else
      v16 = *(PVOID *)(a3 + 24);
    if ( v16 )
    {
      v17 = 36;
      if ( *(_DWORD *)(a3 + 16) < 0x24u )
        v17 = *(_DWORD *)(a3 + 16);
      if ( v17 == RtlCompareMemory(v16, (const void *)(v7 + 72), v17) )
        *(_DWORD *)(v3 + 132) |= 0x100u;
    }
  }
  if ( (*(_DWORD *)(v3 + 132) & 0x800) != 0 && (*(_BYTE *)(a3 + 3) & 0x3F) == 1 )
  {
    if ( *(_BYTE *)v10 == 27 )
    {
      if ( (*(_BYTE *)(a3 + 76) & 2) != 0 )
        goto LABEL_39;
    }
    else if ( !*(_BYTE *)v10 && !*(_BYTE *)(v7 + 781) )
    {
      *(_BYTE *)(v7 + 781) = 1;
LABEL_39:
      USBSTOR_QueueMediaChangeNotify(Object, (PVOID)v3);
    }
  }
  if ( (*(_BYTE *)(a3 + 3) & 0x3F) != 1 )
  {
    switch ( *(_BYTE *)(a3 + 3) & 0x3F )
    {
      case 8:
      case 0x11:
      case 0x20:
      case 0x21:
        break;
      case 9:
      case 0xB:
      case 0xE:
        v8 = -1073741643;
        break;
      case 0xA:
        v8 = -1073741667;
        break;
      case 0x12:
        v8 = -2147483643;
        break;
      case 0x15:
      case 0x22:
        v8 = -1073741808;
        break;
      default:
        v8 = -1073741435;
        break;
    }
    *(_DWORD *)(a2 + 48) = v8;
  }
  if ( (*(_DWORD *)(a3 + 12) & 0x80010) != 0 && (unsigned __int8)UsbQueueIsBypassIrp(a2, v7 + 368) )
  {
    UsbQueueClearBypassIrp(v7 + 368);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    USBSTOR_LogEntry(1112621891, Object, v7 + 368, *(int *)(v7 + 668));
  }
  if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 && v7 && *(_BYTE *)(v7 + 816) )
  {
    PerformanceFrequency.QuadPart = 0;
    v31 = 0;
    v22 = KeQueryPerformanceCounter(&PerformanceFrequency);
    LOBYTE(v23) = 0;
    v24 = v22;
    if ( PerformanceFrequency.QuadPart )
    {
      v24.QuadPart = v22.QuadPart - *(_QWORD *)(v7 + 808);
      if ( v24.QuadPart )
      {
        v25 = 1000 * (v24.QuadPart % (unsigned __int64)PerformanceFrequency.QuadPart);
        v24.QuadPart = v25 / PerformanceFrequency.QuadPart
                     + 1000 * (v24.QuadPart / (unsigned __int64)PerformanceFrequency.QuadPart);
        v23 = 10000 * (v25 % PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart + 10000 * v24.QuadPart;
      }
    }
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))IoGetActivityIdIrp)(a2, &v31, (LARGE_INTEGER)v24.QuadPart);
    if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 1) != 0 )
      McTemplateK0uuuuxqbr5upp_EtwWriteTransfer(
        v26,
        *(unsigned __int8 *)(a3 + 10),
        (unsigned int)&v31,
        v27,
        BugCheckOnFailure,
        Priority,
        *(_BYTE *)(v7 + 71),
        v23,
        *(unsigned __int8 *)(a3 + 10),
        (__int64)v10,
        *(_BYTE *)(a3 + 3),
        a2,
        a2);
  }
  return USBSTOR_FxPowerReference(v3, a3, 0);
}

```

## disassembly

```asm
0x140004910  mov     r11, rsp
0x140004913  push    rbx
0x140004914  push    rsi
0x140004915  push    rdi
0x140004916  push    r12
0x140004918  push    r14
0x14000491a  push    r15
0x14000491c  sub     rsp, 98h
0x140004923  mov     rax, cs:__security_cookie
0x14000492a  xor     rax, rsp
0x14000492d  mov     [rsp+0C8h+var_40], rax
0x140004935  mov     rsi, [rcx+40h]
0x140004939  mov     rbx, r8
0x14000493c  mov     rax, [rdx+0B8h]
0x140004943  mov     r14, rdx
0x140004946  mov     [r11+20h], rbp
0x14000494a  mov     [r11-38h], r13
0x14000494e  mov     r13, rcx
0x140004951  lea     rcx, [rsi+0C0h]; PKTIMER
0x140004958  mov     r12, [rax+10h]
0x14000495c  call    cs:__imp_KeCancelTimer
0x140004963  nop     dword ptr [rax+rax+00h]
0x140004968  mov     rax, [rsi+40h]
0x14000496c  lea     rdi, cs:140000000h
0x140004973  mov     ebp, 0C00000C0h
0x140004978  cmp     byte ptr [rax+6], 6
0x14000497c  jz      loc_140004A5C
0x140004982  movzx   eax, byte ptr [rbx+48h]
0x140004986  lea     r15, [rbx+48h]
0x14000498a  cmp     al, [rsi+498h]
0x140004990  jnz     loc_140004C0E
0x140004996  movzx   ecx, byte ptr [rbx+3]
0x14000499a  movzx   eax, cl
0x14000499d  and     al, 3Fh
0x14000499f  cmp     al, 1
0x1400049a1  jnz     loc_140004B09
0x1400049a7  test    dword ptr [rbx+0Ch], 1000000h
0x1400049ae  jnz     loc_140004D02
0x1400049b4  movzx   eax, byte ptr [rbx+3]
0x1400049b8  and     eax, 0FFFFFF3Fh
0x1400049bd  cmp     eax, 1
0x1400049c0  jz      loc_140004A88
0x1400049c6  cmp     eax, 12h
0x1400049c9  jz      loc_140004A88
0x1400049cf  test    dword ptr [rsi+84h], 800h
0x1400049d9  jnz     loc_140004B5B
0x1400049df  movzx   eax, byte ptr [rbx+3]
0x1400049e3  and     eax, 0FFFFFF3Fh
0x1400049e8  cmp     eax, 1
0x1400049eb  jz      short loc_140004A02
0x1400049ed  add     eax, 0FFFFFFF8h; switch 27 cases
0x1400049f0  cmp     eax, 1Ah
0x1400049f3  jbe     loc_140004B37
0x1400049f9  mov     ebp, 0C0000185h; jumptable 0000000140004B4B default case, cases 12,13,15,16,19,20,22-31
0x1400049fe  mov     [r14+30h], ebp; jumptable 0000000140004B4B cases 8,17,32,33
0x140004a02  test    dword ptr [rbx+0Ch], 80010h
0x140004a09  mov     rbp, [rsp+0C8h+arg_18]
0x140004a11  jnz     loc_140004D3F
0x140004a17  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 1
0x140004a1e  mov     r13, [rsp+0C8h+var_38]
0x140004a26  jnz     loc_140004DC3
0x140004a2c  xor     r8d, r8d
0x140004a2f  mov     rdx, rbx
0x140004a32  mov     rcx, rsi
0x140004a35  call    USBSTOR_FxPowerReference
0x140004a3a  mov     rcx, [rsp+0C8h+var_40]
0x140004a42  xor     rcx, rsp; StackCookie
0x140004a45  call    __security_check_cookie
0x140004a4a  add     rsp, 98h
0x140004a51  pop     r15
0x140004a53  pop     r14
0x140004a55  pop     r12
0x140004a57  pop     rdi
0x140004a58  pop     rsi
0x140004a59  pop     rbx
0x140004a5a  retn
0x140004a5c  movzx   eax, byte ptr [rbx+3]
0x140004a60  and     eax, 0FFFFFF3Fh
0x140004a65  cmp     eax, 1
0x140004a68  jz      short loc_140004A7F
0x140004a6a  add     eax, 0FFFFFFF8h; switch 27 cases
0x140004a6d  cmp     eax, 1Ah
0x140004a70  jbe     loc_140004BA4
0x140004a76  mov     eax, 0C0000185h; jumptable 0000000140004BB8 default case, cases 12,13,15,16,19,20,22-31
0x140004a7b  mov     [r14+30h], eax
0x140004a7f  lea     r15, [rbx+48h]
0x140004a83  jmp     loc_140004996
0x140004a88  cmp     byte ptr [rbx+48h], 12h
0x140004a8c  jnz     loc_1400049CF
0x140004a92  test    dword ptr [rsi+84h], 100h
0x140004a9c  setz    al
0x140004a9f  and     al, [rbx+49h]
0x140004aa2  test    al, 1
0x140004aa4  jz      loc_1400049CF
0x140004aaa  mov     rcx, [r14+8]; MemoryDescriptorList
0x140004aae  test    rcx, rcx
0x140004ab1  jnz     loc_140004BD0
0x140004ab7  mov     r9, [rbx+18h]
0x140004abb  test    r9, r9
0x140004abe  jz      loc_1400049CF
0x140004ac4  mov     eax, [rbx+10h]
0x140004ac7  lea     rdx, [r12+48h]; Source2
0x140004acc  mov     ecx, 24h ; '$'
0x140004ad1  cmp     eax, ecx
0x140004ad3  cmovb   ecx, eax
0x140004ad6  mov     edi, ecx
0x140004ad8  mov     r8d, ecx; Length
0x140004adb  mov     rcx, r9; Source1
0x140004ade  call    cs:__imp_RtlCompareMemory
0x140004ae5  nop     dword ptr [rax+rax+00h]
0x140004aea  cmp     rdi, rax
0x140004aed  lea     rdi, cs:140000000h
0x140004af4  jnz     loc_1400049CF
0x140004afa  or      dword ptr [rsi+84h], 100h
0x140004b04  jmp     loc_1400049CF
0x140004b09  test    dword ptr [rbx+0Ch], 100h
0x140004b10  jnz     loc_1400049A7
0x140004b16  or      cl, 40h
0x140004b19  mov     [rbx+3], cl
0x140004b1c  test    r12, r12
0x140004b1f  jz      loc_1400049A7
0x140004b25  lea     rcx, [r12+170h]
0x140004b2d  call    UsbQueueFreeze
0x140004b32  jmp     loc_1400049A7
0x140004b37  cdqe
0x140004b39  movzx   eax, ds:(byte_140017858 - 140000000h)[rdi+rax]
0x140004b41  mov     ecx, ds:(jpt_140004B4B - 140000000h)[rdi+rax*4]
0x140004b48  add     rcx, rdi
0x140004b4b  jmp     rcx; switch jump
0x140004b51  mov     ebp, 80000005h; jumptable 0000000140004B4B case 18
0x140004b56  jmp     loc_1400049FE; jumptable 0000000140004B4B cases 8,17,32,33
0x140004b5b  movzx   eax, byte ptr [rbx+3]
0x140004b5f  and     al, 3Fh
0x140004b61  cmp     al, 1
0x140004b63  jnz     loc_1400049DF
0x140004b69  movzx   eax, byte ptr [r15]
0x140004b6d  cmp     al, 1Bh
0x140004b6f  jz      loc_140004D12
0x140004b75  test    al, al
0x140004b77  jnz     loc_1400049DF
0x140004b7d  cmp     [r12+30Dh], al
0x140004b85  jnz     loc_1400049DF
0x140004b8b  mov     byte ptr [r12+30Dh], 1
0x140004b94  mov     rdx, rsi; Context
0x140004b97  mov     rcx, r13; Object
0x140004b9a  call    USBSTOR_QueueMediaChangeNotify
0x140004b9f  jmp     loc_1400049DF
0x140004ba4  cdqe
0x140004ba6  movzx   eax, ds:(byte_14001788B - 140000000h)[rdi+rax]
0x140004bae  mov     ecx, ds:(jpt_140004BB8 - 140000000h)[rdi+rax*4]
0x140004bb5  add     rcx, rdi
0x140004bb8  jmp     rcx; switch jump
0x140004bbe  mov     eax, 80000005h; jumptable 0000000140004BB8 case 18
0x140004bc3  lea     r15, [rbx+48h]
0x140004bc7  mov     [r14+30h], eax
0x140004bcb  jmp     loc_140004996
0x140004bd0  test    byte ptr [rcx+0Ah], 5
0x140004bd4  jz      short loc_140004BDF
0x140004bd6  mov     r9, [rcx+18h]
0x140004bda  jmp     loc_140004ABB
0x140004bdf  mov     [rsp+0C8h+Priority], 40000010h; Priority
0x140004be7  xor     r9d, r9d; RequestedAddress
0x140004bea  xor     edx, edx; AccessMode
0x140004bec  mov     [rsp+0C8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004bf4  mov     r8d, 1; CacheType
0x140004bfa  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004c01  nop     dword ptr [rax+rax+00h]
0x140004c06  mov     r9, rax
0x140004c09  jmp     loc_140004ABB
0x140004c0e  cmp     al, 5Ah ; 'Z'
0x140004c10  jnz     short loc_140004C46
0x140004c12  movzx   eax, byte ptr [rbx+3]
0x140004c16  and     eax, 0FFFFFF3Fh
0x140004c1b  cmp     eax, 1
0x140004c1e  jnz     loc_140004CA7
0x140004c24  cmp     dword ptr [rbx+10h], 8
0x140004c28  jb      short loc_140004C46
0x140004c2a  mov     rcx, [r14+8]; MemoryDescriptorList
0x140004c2e  test    rcx, rcx
0x140004c31  jz      short loc_140004CB1
0x140004c33  test    byte ptr [rcx+0Ah], 5
0x140004c37  jz      short loc_140004C56
0x140004c39  mov     rcx, [rcx+18h]
0x140004c3d  test    rcx, rcx
0x140004c40  jnz     short loc_140004CB5
0x140004c42  mov     byte ptr [rbx+3], 4
0x140004c46  movups  xmm0, xmmword ptr [rsi+498h]
0x140004c4d  movups  xmmword ptr [r15], xmm0
0x140004c51  jmp     loc_140004996
0x140004c56  mov     [rsp+0C8h+Priority], 40000010h; Priority
0x140004c5e  xor     r9d, r9d; RequestedAddress
0x140004c61  xor     edx, edx; AccessMode
0x140004c63  mov     [rsp+0C8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140004c6b  mov     r8d, 1; CacheType
0x140004c71  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140004c78  nop     dword ptr [rax+rax+00h]
0x140004c7d  mov     rcx, rax
0x140004c80  jmp     short loc_140004C3D
0x140004c82  mov     eax, ebp; jumptable 0000000140004BB8 cases 8,17,32,33
0x140004c84  jmp     loc_140004A7B
0x140004c89  mov     eax, 0C00000B5h; jumptable 0000000140004BB8 cases 9,11,14
0x140004c8e  jmp     loc_140004A7B
0x140004c93  mov     eax, 0C000009Dh; jumptable 0000000140004BB8 case 10
0x140004c98  jmp     loc_140004A7B
0x140004c9d  mov     eax, 0C0000010h; jumptable 0000000140004BB8 cases 21,34
0x140004ca2  jmp     loc_140004A7B
0x140004ca7  cmp     eax, 12h
0x140004caa  jnz     short loc_140004C46
0x140004cac  jmp     loc_140004C24
0x140004cb1  mov     rcx, [rbx+18h]
0x140004cb5  movzx   eax, byte ptr [rcx+1]
0x140004cb9  lea     rdx, [rcx+8]; Src
0x140004cbd  mov     [rcx], al
0x140004cbf  movzx   eax, byte ptr [rcx+2]
0x140004cc3  mov     [rcx+1], al
0x140004cc6  movzx   eax, byte ptr [rcx+3]
0x140004cca  mov     [rcx+2], al
0x140004ccd  movzx   eax, byte ptr [rcx+7]
0x140004cd1  mov     [rcx+3], al
0x140004cd4  add     rcx, 4; void *
0x140004cd8  mov     r8d, [rbx+10h]
0x140004cdc  sub     r8, 8; Size
0x140004ce0  call    memmove
0x140004ce5  add     dword ptr [rbx+10h], 0FFFFFFFCh
0x140004ce9  mov     eax, 12h
0x140004cee  cmp     byte ptr [rbx+3], 0
0x140004cf2  mov     ecx, 92h
0x140004cf7  cmovl   eax, ecx
0x140004cfa  mov     [rbx+3], al
0x140004cfd  jmp     loc_140004C46
0x140004d02  mov     r8, rbx
0x140004d05  mov     rdx, r14
0x140004d08  call    USBSTOR_SetModeSenseDataProtect
0x140004d0d  jmp     loc_1400049B4
0x140004d12  test    byte ptr [rbx+4Ch], 2
0x140004d16  jz      loc_1400049DF
0x140004d1c  jmp     loc_140004B94
0x140004d21  mov     ebp, 0C00000B5h; jumptable 0000000140004B4B cases 9,11,14
0x140004d26  jmp     loc_1400049FE; jumptable 0000000140004B4B cases 8,17,32,33
0x140004d2b  mov     ebp, 0C000009Dh; jumptable 0000000140004B4B case 10
0x140004d30  jmp     loc_1400049FE; jumptable 0000000140004B4B cases 8,17,32,33
0x140004d35  mov     ebp, 0C0000010h; jumptable 0000000140004B4B cases 21,34
0x140004d3a  jmp     loc_1400049FE; jumptable 0000000140004B4B cases 8,17,32,33
0x140004d3f  lea     rdx, [r12+170h]
0x140004d47  mov     rcx, r14
0x140004d4a  call    UsbQueueIsBypassIrp
0x140004d4f  test    al, al
0x140004d51  jz      loc_140004A17
0x140004d57  lea     rcx, [r12+170h]
0x140004d5f  call    UsbQueueClearBypassIrp
0x140004d64  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d6b  lea     rax, WPP_GLOBAL_Control
0x140004d72  cmp     rcx, rax
0x140004d75  jz      short loc_140004DA1
0x140004d77  mov     eax, [rcx+2Ch]
0x140004d7a  test    al, 20h
0x140004d7c  jz      short loc_140004DA1
0x140004d7e  cmp     byte ptr [rcx+29h], 4
0x140004d82  jb      short loc_140004DA1
0x140004d84  mov     r9d, [r12+29Ch]
0x140004d8c  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140004d93  mov     rcx, [rcx+18h]
0x140004d97  mov     edx, 4Bh ; 'K'
0x140004d9c  call    WPP_SF_d
0x140004da1  movsxd  r9, dword ptr [r12+29Ch]
0x140004da9  lea     r8, [r12+170h]
0x140004db1  mov     rdx, r13
0x140004db4  mov     ecx, 42514343h
0x140004db9  call    USBSTOR_LogEntry
0x140004dbe  jmp     loc_140004A17
0x140004dc3  test    r12, r12
0x140004dc6  jz      loc_140004A2C
0x140004dcc  cmp     byte ptr [r12+330h], 0
0x140004dd5  jz      loc_140004A2C
0x140004ddb  xorps   xmm0, xmm0
0x140004dde  mov     qword ptr [rsp+0C8h+PerformanceFrequency], 0
0x140004de7  lea     rcx, [rsp+0C8h+PerformanceFrequency]; PerformanceFrequency
0x140004dec  movups  [rsp+0C8h+var_50], xmm0
0x140004df1  call    cs:__imp_KeQueryPerformanceCounter
0x140004df8  nop     dword ptr [rax+rax+00h]
0x140004dfd  mov     rcx, qword ptr [rsp+0C8h+PerformanceFrequency]
0x140004e02  xor     edi, edi
0x140004e04  mov     r8, rax
0x140004e07  test    rcx, rcx
0x140004e0a  jz      short loc_140004E5D
0x140004e0c  sub     r8, [r12+328h]
0x140004e14  jz      short loc_140004E5D
0x140004e16  xor     edx, edx
0x140004e18  mov     rax, r8
0x140004e1b  div     rcx
0x140004e1e  mov     rax, r8
0x140004e21  imul    r9, rdx, 3E8h
0x140004e28  xor     edx, edx
0x140004e2a  div     rcx
0x140004e2d  xor     edx, edx
0x140004e2f  imul    r8, rax, 3E8h
0x140004e36  mov     rax, r9
0x140004e39  div     rcx
0x140004e3c  xor     edx, edx
0x140004e3e  add     r8, rax
  ... truncated ...
```

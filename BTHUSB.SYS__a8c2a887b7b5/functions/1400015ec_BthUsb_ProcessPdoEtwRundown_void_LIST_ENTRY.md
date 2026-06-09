# BthUsb_ProcessPdoEtwRundown(void *,_LIST_ENTRY *)

- ea: `0x1400015ec`
- end: `0x14000171d`
- name: `?BthUsb_ProcessPdoEtwRundown@@YAEPEAXPEAU_LIST_ENTRY@@@Z`
- size: `305`
- prototype: `unsigned __int8 __fastcall(void *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001570`

## callees

- `0x1400015ec`
- `0x14000ddc0`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400016f9`
- `ntoskrnl!EtwWrite` at `0x1400016f9`

## pseudocode

```c
unsigned __int8 __fastcall BthUsb_ProcessPdoEtwRundown(void *a1, struct _LIST_ENTRY *a2)
{
  _LIST_ENTRY *v3; // r10
  _LIST_ENTRY *Flink; // rcx
  unsigned int v5; // edx
  unsigned int v6; // r9d
  unsigned int v7; // r11d
  __int16 v8; // ax
  unsigned int v9; // ecx
  unsigned int Flink_low; // eax
  _LIST_ENTRY *v11; // rcx
  int Blink_low; // r9d
  int v14; // [rsp+30h] [rbp-9h] BYREF
  __int128 v15; // [rsp+38h] [rbp-1h] BYREF
  int v16; // [rsp+48h] [rbp+Fh]
  _BYTE UserData[24]; // [rsp+50h] [rbp+17h] BYREF
  __int128 v18; // [rsp+68h] [rbp+2Fh]
  __int64 v19; // [rsp+78h] [rbp+3Fh]

  memset(UserData, 0, sizeof(UserData));
  v14 = 0;
  v19 = 0;
  v15 = 0;
  v16 = 0;
  v3 = 0;
  Flink = a2[-66].Flink;
  v5 = 0;
  v6 = BYTE1(a2[1].Flink);
  v7 = BYTE2(a2[1].Flink);
  v18 = 0;
  LOWORD(v14) = Flink->Blink;
  v8 = WORD1(Flink->Blink);
  v9 = BYTE3(a2[1].Flink);
  HIWORD(v14) = v8;
  *(_QWORD *)UserData = &v14;
  Flink_low = LOBYTE(a2[1].Flink);
  *(_QWORD *)&UserData[8] = 4;
  *(_QWORD *)&v15 = __PAIR64__(v6, Flink_low);
  *((_QWORD *)&v15 + 1) = __PAIR64__(v9, v7);
  if ( !Flink_low || !v6 || !v7 || (v16 = 1, v9) )
    v16 = 0;
  v11 = a2[-70].Flink;
  *(_QWORD *)&UserData[16] = &v15;
  *(_QWORD *)&v18 = 20;
  if ( v11 )
  {
    Blink_low = LOWORD(a2[-71].Blink);
    if ( (_WORD)Blink_low )
    {
      v3 = v11;
      v5 = Blink_low + 2;
    }
  }
  v19 = v5;
  *((_QWORD *)&v18 + 1) = v3;
  EtwWrite(g_EtwRegHandle, &BTHUSB_ETW_EVENT_HC_INFORMATION, 0, 3u, (PEVENT_DATA_DESCRIPTOR)UserData);
  return 1;
}

```

## disassembly

```asm
0x1400015ec  push    rbp
0x1400015ee  lea     rbp, [rsp-57h]
0x1400015f3  sub     rsp, 90h
0x1400015fa  mov     rax, cs:__security_cookie
0x140001601  xor     rax, rsp
0x140001604  mov     [rbp+57h+var_10], rax
0x140001608  xor     eax, eax
0x14000160a  mov     qword ptr [rbp+57h+var_40], 0
0x140001612  mov     r8, rdx
0x140001615  mov     [rbp+57h+var_60], eax
0x140001618  mov     [rbp+57h+var_18], rax
0x14000161c  xorps   xmm0, xmm0
0x14000161f  movups  [rbp+57h+var_58], xmm0
0x140001623  mov     [rbp+57h+var_48], eax
0x140001626  xor     r10d, r10d
0x140001629  mov     rcx, [r8-420h]
0x140001630  xor     edx, edx
0x140001632  movzx   r9d, byte ptr [r8+11h]
0x140001637  movzx   r11d, byte ptr [r8+12h]
0x14000163c  movups  xmmword ptr [rbp+57h+var_40+8], xmm0
0x140001640  movups  [rbp+57h+var_28], xmm0
0x140001644  movzx   eax, word ptr [rcx+8]
0x140001648  mov     word ptr [rbp+57h+var_60], ax
0x14000164c  movzx   eax, word ptr [rcx+0Ah]
0x140001650  movzx   ecx, byte ptr [r8+13h]
0x140001655  mov     word ptr [rbp+57h+var_60+2], ax
0x140001659  lea     rax, [rbp+57h+var_60]
0x14000165d  mov     qword ptr [rbp+57h+var_40], rax
0x140001661  movzx   eax, byte ptr [r8+10h]
0x140001666  mov     qword ptr [rbp+57h+var_40+8], 4
0x14000166e  mov     dword ptr [rbp+57h+var_58], eax
0x140001671  mov     dword ptr [rbp+57h+var_58+4], r9d
0x140001675  mov     dword ptr [rbp+57h+var_58+8], r11d
0x140001679  mov     dword ptr [rbp+57h+var_58+0Ch], ecx
0x14000167c  test    eax, eax
0x14000167e  jz      short loc_140001695
0x140001680  test    r9d, r9d
0x140001683  jz      short loc_140001695
0x140001685  test    r11d, r11d
0x140001688  jz      short loc_140001695
0x14000168a  mov     [rbp+57h+var_48], 1
0x140001691  test    ecx, ecx
0x140001693  jz      short loc_140001698
0x140001695  mov     [rbp+57h+var_48], edx
0x140001698  mov     rcx, [r8-460h]
0x14000169f  lea     rax, [rbp+57h+var_58]
0x1400016a3  mov     qword ptr [rbp+57h+var_40+10h], rax
0x1400016a7  mov     qword ptr [rbp+57h+var_28], 14h
0x1400016af  test    rcx, rcx
0x1400016b2  jz      short loc_1400016CB
0x1400016b4  movzx   r9d, word ptr [r8-468h]
0x1400016bc  xor     eax, eax
0x1400016be  cmp     ax, r9w
0x1400016c2  jz      short loc_1400016CB
0x1400016c4  mov     r10, rcx
0x1400016c7  lea     edx, [r9+2]
0x1400016cb  lea     rcx, [rbp+57h+var_40]
0x1400016cf  mov     dword ptr [rbp+57h+var_18], edx
0x1400016d2  mov     [rsp+90h+UserData], rcx; UserData
0x1400016d7  lea     rdx, BTHUSB_ETW_EVENT_HC_INFORMATION; EventDescriptor
0x1400016de  mov     rcx, cs:?g_EtwRegHandle@@3_KA; RegHandle
0x1400016e5  mov     r9d, 3; UserDataCount
0x1400016eb  xor     r8d, r8d; ActivityId
0x1400016ee  mov     qword ptr [rbp+57h+var_28+8], r10
0x1400016f2  mov     dword ptr [rbp+57h+var_18+4], 0
0x1400016f9  call    cs:__imp_EtwWrite
0x140001700  nop     dword ptr [rax+rax+00h]
0x140001705  mov     al, 1
0x140001707  mov     rcx, [rbp+57h+var_10]
0x14000170b  xor     rcx, rsp; StackCookie
0x14000170e  call    __security_check_cookie
0x140001713  add     rsp, 90h
0x14000171a  pop     rbp
0x14000171b  retn
```

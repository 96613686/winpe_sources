# HCI_RegUpdateScanEnable(HCI_INTERFACE *,void *,_KEY_VALUE_PARTIAL_INFORMATION *,uchar,_GUID *)

- ea: `0x1401d0900`
- end: `0x1401d0b4c`
- name: `?HCI_RegUpdateScanEnable@@YAJPEAUHCI_INTERFACE@@PEAXPEAU_KEY_VALUE_PARTIAL_INFORMATION@@EPEAU_GUID@@@Z`
- size: `588`
- prototype: `int(struct HCI_INTERFACE *, void *, struct _KEY_VALUE_PARTIAL_INFORMATION *, unsigned __int8, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x140005690`
- `0x14001be50`
- `0x1400a9938`
- `0x1401d0900`
- `0x140209540`

## import_xrefs

- `ntoskrnl!ZwDeleteValueKey` at `0x1401d0a5b`
- `ntoskrnl!ZwDeleteValueKey` at `0x1401d0a5b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d0a47`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d0a47`

## string_xrefs

- `0x1401d09b8`: `Write Scan Enable`
- `0x1401d0a3b`: `Write Scan Enable`

## pseudocode

```c
__int64 __fastcall HCI_RegUpdateScanEnable(
        struct HCI_INTERFACE *a1,
        void *a2,
        struct _KEY_VALUE_PARTIAL_INFORMATION *a3)
{
  char v3; // r12
  void *v4; // r15
  char v6; // bl
  __int16 DeviceType; // ax
  RECORDER_LOG__ **p_IfrLog; // rsi
  int v9; // edx
  unsigned int KeyValueUlong; // r14d
  __int64 *v11; // r8
  int v12; // r8d
  __int16 v13; // ax
  __int64 *v14; // rdx
  int v16; // [rsp+28h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-58h]

  v3 = (char)a3;
  DestinationString = 0;
  v4 = a2;
  v6 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(a2) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(a2) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)a2 || DeviceType )
  {
    p_IfrLog = &a1->IfrLog;
    WPP_RECORDER_AND_TRACE_SF_qiq(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      DeviceType != 0,
      a1->IfrLog,
      5,
      2,
      15,
      (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
      (char)a1,
      (char)v4,
      (char)a3);
  }
  else
  {
    p_IfrLog = &a1->IfrLog;
  }
  KeyValueUlong = BthQueryKeyValueUlong(v4);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v9) = 0;
  v11 = WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids;
  LOBYTE(v11) = 1;
  WPP_RECORDER_AND_TRACE_SF_d(
    WPP_GLOBAL_Control->AttachedDevice,
    v9,
    (_DWORD)v11,
    (unsigned int)*p_IfrLog,
    4,
    2,
    17,
    (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
    0);
  a1->RegistryScanEnableFlags = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v6 = 0;
  v13 = WPP_GLOBAL_Control->DeviceType;
  if ( v6 || v13 )
  {
    v14 = WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids;
    LOBYTE(v14) = v6;
    LOBYTE(v12) = v13 != 0;
    WPP_RECORDER_AND_TRACE_SF_qqqD(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v14,
      v12,
      a1->IfrLog,
      5,
      v16,
      18,
      (__int64)WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids,
      (char)a1,
      (char)v4,
      v3,
      KeyValueUlong);
  }
  return KeyValueUlong;
}

```

## disassembly

```asm
0x1401d0900  mov     byte ptr [rsp+arg_18], r9b
0x1401d0905  push    rbx
0x1401d0906  push    rbp
0x1401d0907  push    rsi
0x1401d0908  push    rdi
0x1401d0909  push    r12
0x1401d090b  push    r13
0x1401d090d  push    r14
0x1401d090f  push    r15
0x1401d0911  sub     rsp, 78h
0x1401d0915  xorps   xmm0, xmm0
0x1401d0918  mov     r12, r8
0x1401d091b  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x1401d0920  mov     r15, rdx
0x1401d0923  mov     rdi, rcx
0x1401d0926  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d092d  xor     r13d, r13d
0x1401d0930  mov     eax, [rcx+2Ch]
0x1401d0933  lea     ebx, [r13+1]
0x1401d0937  test    al, 2
0x1401d0939  jz      short loc_1401D0943
0x1401d093b  cmp     byte ptr [rcx+29h], 5
0x1401d093f  mov     dl, bl
0x1401d0941  jnb     short loc_1401D0946
0x1401d0943  mov     dl, r13b
0x1401d0946  movzx   eax, word ptr [rcx+48h]
0x1401d094a  lea     r9, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0951  test    ax, ax
0x1401d0954  setnz   r8b
0x1401d0958  test    dl, dl
0x1401d095a  jnz     short loc_1401D096A
0x1401d095c  test    ax, ax
0x1401d095f  jnz     short loc_1401D096A
0x1401d0961  lea     rsi, [rdi+10B0h]
0x1401d0968  jmp     short loc_1401D09A5
0x1401d096a  mov     rcx, [rcx+18h]
0x1401d096e  lea     rsi, [rdi+10B0h]
0x1401d0975  mov     [rsp+0B8h+var_68], r12
0x1401d097a  mov     [rsp+0B8h+var_70], r15
0x1401d097f  mov     [rsp+0B8h+var_78], rdi
0x1401d0984  mov     [rsp+0B8h+var_80], r9
0x1401d0989  mov     r9, [rsi]
0x1401d098c  mov     [rsp+0B8h+var_88], 0Fh
0x1401d0993  mov     [rsp+0B8h+var_90], 2
0x1401d099b  mov     [rsp+0B8h+var_98], 5
0x1401d09a0  call    WPP_RECORDER_AND_TRACE_SF_qiq
0x1401d09a5  lea     r9, [rsp+0B8h+arg_18]
0x1401d09ad  mov     [rsp+0B8h+arg_18], r13d
0x1401d09b5  mov     r8, r12
0x1401d09b8  lea     rdx, aWriteScanEnabl; "Write Scan Enable"
0x1401d09bf  mov     rcx, r15; KeyHandle
0x1401d09c2  call    BthQueryKeyValueUlong
0x1401d09c7  mov     ebp, [rsp+0B8h+arg_18]
0x1401d09ce  mov     r14d, eax
0x1401d09d1  test    eax, eax
0x1401d09d3  js      loc_1401D0A6A
0x1401d09d9  test    ebp, 0FFFFFFFCh
0x1401d09df  jz      loc_1401D0A6A
0x1401d09e5  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d09ec  mov     ecx, [r10+2Ch]
0x1401d09f0  test    cl, 2
0x1401d09f3  jz      short loc_1401D09FE
0x1401d09f5  cmp     byte ptr [r10+29h], 3
0x1401d09fa  mov     dl, bl
0x1401d09fc  jnb     short loc_1401D0A01
0x1401d09fe  mov     dl, r13b
0x1401d0a01  mov     dword ptr [rsp+0B8h+var_78], ebp
0x1401d0a05  lea     rcx, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0a0c  mov     [rsp+0B8h+var_80], rcx
0x1401d0a11  lea     rsi, [rdi+10B0h]
0x1401d0a18  mov     r9, [rsi]
0x1401d0a1b  mov     r8b, bl
0x1401d0a1e  mov     rcx, [r10+18h]
0x1401d0a22  mov     [rsp+0B8h+var_88], 10h
0x1401d0a29  mov     [rsp+0B8h+var_90], 2
0x1401d0a31  mov     [rsp+0B8h+var_98], 3
0x1401d0a36  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401d0a3b  lea     rdx, aWriteScanEnabl; "Write Scan Enable"
0x1401d0a42  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1401d0a47  call    cs:__imp_RtlInitUnicodeString
0x1401d0a4e  nop     dword ptr [rax+rax+00h]
0x1401d0a53  lea     rdx, [rsp+0B8h+DestinationString]; ValueName
0x1401d0a58  mov     rcx, r15; KeyHandle
0x1401d0a5b  call    cs:__imp_ZwDeleteValueKey
0x1401d0a62  nop     dword ptr [rax+rax+00h]
0x1401d0a67  mov     ebp, r13d
0x1401d0a6a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d0a71  mov     eax, [rcx+2Ch]
0x1401d0a74  test    al, 2
0x1401d0a76  jz      short loc_1401D0A80
0x1401d0a78  cmp     byte ptr [rcx+29h], 4
0x1401d0a7c  mov     dl, bl
0x1401d0a7e  jnb     short loc_1401D0A83
0x1401d0a80  mov     dl, r13b
0x1401d0a83  mov     r9, [rsi]
0x1401d0a86  lea     r8, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0a8d  mov     rcx, [rcx+18h]
0x1401d0a91  mov     dword ptr [rsp+0B8h+var_78], ebp
0x1401d0a95  mov     [rsp+0B8h+var_80], r8
0x1401d0a9a  mov     r8b, bl
0x1401d0a9d  mov     [rsp+0B8h+var_88], 11h
0x1401d0aa4  mov     [rsp+0B8h+var_90], 2
0x1401d0aac  mov     [rsp+0B8h+var_98], 4
0x1401d0ab1  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401d0ab6  and     bpl, bl
0x1401d0ab9  mov     [rdi+0F14h], bpl
0x1401d0ac0  jz      short loc_1401D0ACE
0x1401d0ac2  add     [rdi+0F10h], ebx
0x1401d0ac8  add     [rdi+0F0Ch], ebx
0x1401d0ace  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401d0ad5  mov     eax, [rcx+2Ch]
0x1401d0ad8  test    al, 2
0x1401d0ada  jz      short loc_1401D0AE2
0x1401d0adc  cmp     byte ptr [rcx+29h], 5
0x1401d0ae0  jnb     short loc_1401D0AE5
0x1401d0ae2  mov     bl, r13b
0x1401d0ae5  movzx   eax, word ptr [rcx+48h]
0x1401d0ae9  test    ax, ax
0x1401d0aec  setnz   r8b
0x1401d0af0  test    bl, bl
0x1401d0af2  jnz     short loc_1401D0AF9
0x1401d0af4  test    ax, ax
0x1401d0af7  jz      short loc_1401D0B37
0x1401d0af9  mov     r9, [rdi+10B0h]
0x1401d0b00  lea     rdx, WPP_d1c492af4e1032b0c43eea88fb902046_Traceguids
0x1401d0b07  mov     rcx, [rcx+18h]
0x1401d0b0b  mov     [rsp+0B8h+var_60], r14d
0x1401d0b10  mov     [rsp+0B8h+var_68], r12
0x1401d0b15  mov     [rsp+0B8h+var_70], r15
0x1401d0b1a  mov     [rsp+0B8h+var_78], rdi
0x1401d0b1f  mov     [rsp+0B8h+var_80], rdx
0x1401d0b24  mov     dl, bl
0x1401d0b26  mov     [rsp+0B8h+var_88], 12h
0x1401d0b2d  mov     [rsp+0B8h+var_98], 5
0x1401d0b32  call    WPP_RECORDER_AND_TRACE_SF_qqqD
0x1401d0b37  mov     eax, r14d
0x1401d0b3a  add     rsp, 78h
0x1401d0b3e  pop     r15
0x1401d0b40  pop     r14
0x1401d0b42  pop     r13
0x1401d0b44  pop     r12
0x1401d0b46  pop     rdi
0x1401d0b47  pop     rsi
0x1401d0b48  pop     rbp
0x1401d0b49  pop     rbx
0x1401d0b4a  retn
```

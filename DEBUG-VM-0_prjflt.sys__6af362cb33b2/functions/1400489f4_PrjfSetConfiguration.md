# PrjfSetConfiguration

- ea: `0x1400489f4`
- end: `0x140048d44`
- name: `PrjfSetConfiguration`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400484e0`

## callees

- `0x14000ba20`
- `0x14000d128`
- `0x1400489f4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140048a93`
- `ntoskrnl!ZwOpenKey` at `0x140048b50`
- `ntoskrnl!ZwOpenKey` at `0x140048a93`
- `ntoskrnl!ZwOpenKey` at `0x140048b50`
- `ntoskrnl!ZwQueryValueKey` at `0x140048bd7`
- `ntoskrnl!ZwQueryValueKey` at `0x140048c5e`
- `ntoskrnl!ZwQueryValueKey` at `0x140048bd7`
- `ntoskrnl!ZwQueryValueKey` at `0x140048c5e`
- `ntoskrnl!ZwClose` at `0x140048cff`
- `ntoskrnl!ZwClose` at `0x140048d14`
- `ntoskrnl!ZwClose` at `0x140048cff`
- `ntoskrnl!ZwClose` at `0x140048d14`

## string_xrefs

- `0x140048a6b`: `NegativePathCacheInitialBucketCount`

## pseudocode

```c
__int64 __fastcall PrjfSetConfiguration(struct _UNICODE_STRING *a1)
{
  int v1; // edx
  NTSTATUS v2; // ebx
  int v3; // r8d
  int v4; // edx
  int v5; // r8d
  int v6; // edx
  int v7; // r8d
  int v8; // r8d
  int v9; // edx
  char v11; // [rsp+50h] [rbp-59h]
  ULONG ResultLength; // [rsp+60h] [rbp-49h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-41h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v15[2]; // [rsp+78h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+88h] [rbp-21h] BYREF
  struct _UNICODE_STRING v17; // [rsp+98h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-1h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+D8h] [rbp+2Fh] BYREF
  int v20; // [rsp+E4h] [rbp+3Bh]

  ObjectAttributes.ObjectName = a1;
  KeyHandle = 0;
  Handle = 0;
  ResultLength = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v15[1] = L"Parameters";
  v15[0] = 1441812;
  ValueName.Buffer = L"DebugOptions";
  v17.Buffer = L"NegativePathCacheInitialBucketCount";
  *(_QWORD *)&ValueName.Length = 1703960;
  *(_QWORD *)&v17.Length = 4718662;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v2 >= 0 )
  {
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v15;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v2 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
    if ( v2 >= 0 )
    {
      v2 = ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength);
      if ( v2 >= 0 )
      {
        v2 = ZwQueryValueKey(Handle, &v17, KeyValuePartialInformation, KeyValueInformation, 0x14u, &ResultLength);
        if ( v2 >= 0 )
        {
          v9 = v20;
        }
        else
        {
          v2 = 0;
          v9 = 0x2000;
        }
        dword_14001ABC8 = v9;
        if ( (xmmword_14001A3E0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v11 = v9;
          LOBYTE(v9) = xmmword_14001A3E0 & 2;
          LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDL(
            1025,
            v9,
            v8,
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            4,
            1,
            59,
            (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
            (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
            106,
            v11);
        }
      }
      else if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = xmmword_14001A3D0 & 2;
        LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          513,
          v6,
          v7,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          1,
          58,
          (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
          79,
          v2);
      }
    }
    else if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = xmmword_14001A3D0 & 2;
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        513,
        v4,
        v5,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        1,
        57,
        (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        62,
        v2);
    }
  }
  else if ( (xmmword_14001A3D0 & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v1) = xmmword_14001A3D0 & 2;
    LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      513,
      v1,
      v3,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      1,
      56,
      (__int64)WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
      42,
      v2);
  }
  if ( Handle )
    ZwClose(Handle);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400489f4  mov     [rsp-8+arg_8], rbx
0x1400489f9  mov     [rsp-8+arg_10], rsi
0x1400489fe  push    rbp
0x1400489ff  lea     rbp, [rsp-57h]
0x140048a04  sub     rsp, 100h
0x140048a0b  mov     rax, cs:__security_cookie
0x140048a12  xor     rax, rsp
0x140048a15  mov     [rbp+57h+var_10], rax
0x140048a19  xor     eax, eax
0x140048a1b  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x140048a1f  mov     [rbp+57h+KeyHandle], rax
0x140048a23  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140048a27  mov     [rbp+57h+Handle], rax
0x140048a2b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140048a2f  mov     [rbp+57h+var_A0], eax
0x140048a32  xorps   xmm0, xmm0
0x140048a35  lea     esi, [rax+14h]
0x140048a38  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140048a40  lea     rax, aParameters; "Parameters"
0x140048a47  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140048a4f  mov     [rbp+57h+var_80], rax
0x140048a53  mov     edx, 20019h; DesiredAccess
0x140048a58  lea     rax, aDebugoptions; "DebugOptions"
0x140048a5f  mov     [rbp+57h+var_88], 160014h
0x140048a67  mov     [rbp+57h+ValueName.Buffer], rax
0x140048a6b  lea     rax, aNegativepathca; "NegativePathCacheInitialBucketCount"
0x140048a72  mov     [rbp+57h+var_68.Buffer], rax
0x140048a76  mov     qword ptr [rbp+57h+ValueName.Length], 1A0018h
0x140048a7e  mov     qword ptr [rbp+57h+var_68.Length], 480046h
0x140048a86  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140048a8e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140048a93  call    cs:__imp_ZwOpenKey
0x140048a9a  nop     dword ptr [rax+rax+00h]
0x140048a9f  mov     ebx, eax
0x140048aa1  test    eax, eax
0x140048aa3  jns     short loc_140048B1D
0x140048aa5  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140048aab  lea     rax, WPP_RECORDER_INITIALIZED
0x140048ab2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140048ab9  setnz   r8b
0x140048abd  and     dl, 2
0x140048ac0  jnz     short loc_140048ACB
0x140048ac2  test    r8b, r8b
0x140048ac5  jz      loc_140048CF6
0x140048acb  mov     dword ptr [rsp+100h+var_B0], ebx
0x140048acf  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140048ad6  mov     [rsp+100h+var_B8], 0B2Ah
0x140048ade  mov     [rsp+100h+var_C0], rax
0x140048ae3  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140048aea  mov     [rsp+100h+var_C8], rax
0x140048aef  mov     [rsp+100h+var_D0], 38h ; '8'
0x140048af6  mov     r9, cs:WPP_GLOBAL_Control
0x140048afd  mov     ecx, 201h
0x140048b02  mov     dword ptr [rsp+100h+ResultLength], 1
0x140048b0a  mov     byte ptr [rsp+100h+Length], 2
0x140048b0f  mov     r9, [r9+40h]
0x140048b13  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140048b18  jmp     loc_140048CF6
0x140048b1d  mov     rax, [rbp+57h+KeyHandle]
0x140048b21  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140048b25  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140048b29  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x140048b2d  lea     rax, [rbp+57h+var_88]
0x140048b31  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140048b38  xorps   xmm0, xmm0
0x140048b3b  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140048b3f  mov     edx, 20019h; DesiredAccess
0x140048b44  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140048b4b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140048b50  call    cs:__imp_ZwOpenKey
0x140048b57  nop     dword ptr [rax+rax+00h]
0x140048b5c  mov     ebx, eax
0x140048b5e  test    eax, eax
0x140048b60  jns     short loc_140048BB8
0x140048b62  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140048b68  lea     rax, WPP_RECORDER_INITIALIZED
0x140048b6f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140048b76  setnz   r8b
0x140048b7a  and     dl, 2
0x140048b7d  jnz     short loc_140048B88
0x140048b7f  test    r8b, r8b
0x140048b82  jz      loc_140048CF6
0x140048b88  mov     dword ptr [rsp+100h+var_B0], ebx
0x140048b8c  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140048b93  mov     [rsp+100h+var_B8], 0B3Eh
0x140048b9b  mov     [rsp+100h+var_C0], rax
0x140048ba0  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140048ba7  mov     [rsp+100h+var_C8], rax
0x140048bac  mov     [rsp+100h+var_D0], 39h ; '9'
0x140048bb3  jmp     loc_140048AF6
0x140048bb8  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140048bbc  lea     rax, [rbp+57h+var_A0]
0x140048bc0  mov     [rsp+100h+ResultLength], rax; ResultLength
0x140048bc5  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140048bc9  mov     r8d, 2; KeyValueInformationClass
0x140048bcf  mov     [rsp+100h+Length], esi; Length
0x140048bd3  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140048bd7  call    cs:__imp_ZwQueryValueKey
0x140048bde  nop     dword ptr [rax+rax+00h]
0x140048be3  mov     ebx, eax
0x140048be5  test    eax, eax
0x140048be7  jns     short loc_140048C3F
0x140048be9  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140048bef  lea     rax, WPP_RECORDER_INITIALIZED
0x140048bf6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140048bfd  setnz   r8b
0x140048c01  and     dl, 2
0x140048c04  jnz     short loc_140048C0F
0x140048c06  test    r8b, r8b
0x140048c09  jz      loc_140048CF6
0x140048c0f  mov     dword ptr [rsp+100h+var_B0], ebx
0x140048c13  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140048c1a  mov     [rsp+100h+var_B8], 0B4Fh
0x140048c22  mov     [rsp+100h+var_C0], rax
0x140048c27  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140048c2e  mov     [rsp+100h+var_C8], rax
0x140048c33  mov     [rsp+100h+var_D0], 3Ah ; ':'
0x140048c3a  jmp     loc_140048AF6
0x140048c3f  mov     rcx, [rbp+57h+Handle]; KeyHandle
0x140048c43  lea     rax, [rbp+57h+var_A0]
0x140048c47  mov     [rsp+100h+ResultLength], rax; ResultLength
0x140048c4c  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140048c50  mov     r8d, 2; KeyValueInformationClass
0x140048c56  mov     [rsp+100h+Length], esi; Length
0x140048c5a  lea     rdx, [rbp+57h+var_68]; ValueName
0x140048c5e  call    cs:__imp_ZwQueryValueKey
0x140048c65  nop     dword ptr [rax+rax+00h]
0x140048c6a  mov     ebx, eax
0x140048c6c  test    eax, eax
0x140048c6e  jns     short loc_140048C79
0x140048c70  xor     ebx, ebx
0x140048c72  mov     edx, 2000h
0x140048c77  jmp     short loc_140048C7C
0x140048c79  mov     edx, [rbp+57h+var_1C]
0x140048c7c  mov     cs:dword_14001ABC8, edx
0x140048c82  mov     r10b, byte ptr cs:xmmword_14001A3E0
0x140048c89  lea     rax, WPP_RECORDER_INITIALIZED
0x140048c90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140048c97  setnz   r8b
0x140048c9b  and     r10b, 2
0x140048c9f  jnz     short loc_140048CA6
0x140048ca1  test    r8b, r8b
0x140048ca4  jz      short loc_140048CF6
0x140048ca6  mov     r9, cs:WPP_GLOBAL_Control
0x140048cad  lea     rax, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140048cb4  mov     dword ptr [rsp+100h+var_B0], edx
0x140048cb8  mov     ecx, 401h
0x140048cbd  mov     [rsp+100h+var_B8], 0B6Ah
0x140048cc5  mov     dl, r10b
0x140048cc8  mov     [rsp+100h+var_C0], rax
0x140048ccd  lea     rax, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x140048cd4  mov     r9, [r9+40h]
0x140048cd8  mov     [rsp+100h+var_C8], rax
0x140048cdd  mov     [rsp+100h+var_D0], 3Bh ; ';'
0x140048ce4  mov     dword ptr [rsp+100h+ResultLength], 1
0x140048cec  mov     byte ptr [rsp+100h+Length], 4
0x140048cf1  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140048cf6  mov     rcx, [rbp+57h+Handle]; Handle
0x140048cfa  test    rcx, rcx
0x140048cfd  jz      short loc_140048D0B
0x140048cff  call    cs:__imp_ZwClose
0x140048d06  nop     dword ptr [rax+rax+00h]
0x140048d0b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140048d0f  test    rcx, rcx
0x140048d12  jz      short loc_140048D20
0x140048d14  call    cs:__imp_ZwClose
0x140048d1b  nop     dword ptr [rax+rax+00h]
0x140048d20  mov     eax, ebx
0x140048d22  mov     rcx, [rbp+57h+var_10]
0x140048d26  xor     rcx, rsp; StackCookie
0x140048d29  call    __security_check_cookie
0x140048d2e  lea     r11, [rsp+100h+var_s0]
0x140048d36  mov     rbx, [r11+18h]
0x140048d3a  mov     rsi, [r11+20h]
0x140048d3e  mov     rsp, r11
0x140048d41  pop     rbp
0x140048d42  retn
```

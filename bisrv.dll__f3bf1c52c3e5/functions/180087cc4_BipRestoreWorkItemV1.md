# BipRestoreWorkItemV1

- ea: `0x180087cc4`
- end: `0x1800882ac`
- name: `BipRestoreWorkItemV1`
- size: `1512`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800882b4`

## callees

- `0x180009100`
- `0x180025a0c`
- `0x1800260e8`
- `0x1800263b8`
- `0x180026f8c`
- `0x180030a80`
- `0x180030f24`
- `0x180049844`
- `0x18004c4cc`
- `0x18005df20`
- `0x180078914`
- `0x180087cc4`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180087de0`
- `ntdll!NtOpenKey` at `0x180087de0`
- `ntdll!RtlFreeUnicodeString` at `0x180088266`
- `ntdll!RtlFreeUnicodeString` at `0x180088270`
- `ntdll!RtlFreeUnicodeString` at `0x18008827a`
- `ntdll!RtlFreeUnicodeString` at `0x180088266`
- `ntdll!RtlFreeUnicodeString` at `0x180088270`
- `ntdll!RtlFreeUnicodeString` at `0x18008827a`
- `ntdll!RtlInitUnicodeString` at `0x180087d85`
- `ntdll!RtlInitUnicodeString` at `0x180087d91`
- `ntdll!RtlInitUnicodeString` at `0x180087d9d`
- `ntdll!RtlInitUnicodeString` at `0x180087e2f`
- `ntdll!RtlInitUnicodeString` at `0x180087e79`
- `ntdll!RtlInitUnicodeString` at `0x180087efe`
- `ntdll!RtlInitUnicodeString` at `0x180087f75`
- `ntdll!RtlInitUnicodeString` at `0x180087fd9`
- `ntdll!RtlInitUnicodeString` at `0x180088044`
- `ntdll!RtlInitUnicodeString` at `0x18008810b`
- `ntdll!RtlInitUnicodeString` at `0x180087d85`
- `ntdll!RtlInitUnicodeString` at `0x180087d91`
- `ntdll!RtlInitUnicodeString` at `0x180087d9d`
- `ntdll!RtlInitUnicodeString` at `0x180087e2f`
- `ntdll!RtlInitUnicodeString` at `0x180087e79`
- `ntdll!RtlInitUnicodeString` at `0x180087efe`
- `ntdll!RtlInitUnicodeString` at `0x180087f75`
- `ntdll!RtlInitUnicodeString` at `0x180087fd9`
- `ntdll!RtlInitUnicodeString` at `0x180088044`
- `ntdll!RtlInitUnicodeString` at `0x18008810b`
- `ntdll!RtlFreeHeap` at `0x18008825c`
- `ntdll!RtlFreeHeap` at `0x18008825c`
- `ntdll!NtClose` at `0x180088245`
- `ntdll!NtClose` at `0x180088245`

## string_xrefs

- `0x180088100`: `TaskEntryPoint`

## pseudocode

```c
__int64 __fastcall BipRestoreWorkItemV1(void *a1, struct _GUID *a2, struct _UNICODE_STRING *a3)
{
  struct _BI_CONDITIONAL_EVENT_INFORMATION *v6; // rdi
  unsigned int v7; // r14d
  NTSTATUS v8; // eax
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  struct _UNICODE_STRING *p_UnicodeString; // r15
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v20; // [rsp+88h] [rbp-A8h]
  size_t v21; // [rsp+A0h] [rbp-90h]
  void *KeyHandle; // [rsp+B0h] [rbp-80h] BYREF
  int v23; // [rsp+B8h] [rbp-78h]
  unsigned int v24; // [rsp+BCh] [rbp-74h]
  struct _UNICODE_STRING ValueName; // [rsp+C0h] [rbp-70h] BYREF
  unsigned int v26[4]; // [rsp+D0h] [rbp-60h] BYREF
  __int64 Buf1[2]; // [rsp+E0h] [rbp-50h] BYREF
  struct _UNICODE_STRING v28; // [rsp+F0h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+100h] [rbp-30h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+110h] [rbp-20h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+120h] [rbp-10h] BYREF
  __int64 v32; // [rsp+150h] [rbp+20h] BYREF
  GUID Guid; // [rsp+158h] [rbp+28h] BYREF
  WCHAR v34; // [rsp+170h] [rbp+40h] BYREF
  int v35; // [rsp+172h] [rbp+42h] BYREF

  v23 = 0;
  v24 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(&v34, 0, 0x82u);
  v32 = 0;
  KeyHandle = 0;
  v28 = 0;
  Guid = 0;
  ValueName = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b9992b7a0e48309012f383940558a5f4_Traceguids, a2);
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&UnicodeString, 0);
  RtlInitUnicodeString(&v28, 0);
  KeyHandle = 0;
  Buf1[0] = 0;
  v26[0] = 0;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = 0;
  ObjectAttributes.RootDirectory = a1;
  v7 = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a3;
  v8 = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  v9 = v8;
  if ( v8 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"ActivationType");
    v8 = BipReadRegUlong(KeyHandle, &ValueName);
    v9 = v8;
    if ( v8 >= 0 )
    {
      RtlInitUnicodeString(&ValueName, L"Conditions");
      v8 = BipReadRegMultiSz(KeyHandle, &ValueName, &DestinationString);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( v8 != -1073741772 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = 23;
            goto LABEL_8;
          }
          goto LABEL_60;
        }
      }
      else
      {
        v13 = BipParseConditionString(&DestinationString.Length, (int *)v26, (PVOID *)Buf1);
        v9 = v13;
        if ( v13 < 0 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              WPP_b9992b7a0e48309012f383940558a5f4_Traceguids,
              (unsigned int)v13);
          v6 = (struct _BI_CONDITIONAL_EVENT_INFORMATION *)Buf1[0];
          goto LABEL_60;
        }
        v7 = v26[0];
        v6 = (struct _BI_CONDITIONAL_EVENT_INFORMATION *)Buf1[0];
      }
      RtlInitUnicodeString(&ValueName, L"Flags");
      v8 = BipReadRegUlong(KeyHandle, &ValueName);
      v9 = v8;
      if ( v8 >= 0 )
      {
        RtlInitUnicodeString(&ValueName, L"Name");
        v14 = BipReadRegUnicodeString(KeyHandle, &ValueName, &UnicodeString);
        v9 = 0;
        p_UnicodeString = &UnicodeString;
        if ( v14 == -1073741772 )
          p_UnicodeString = 0;
        else
          v9 = v14;
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = 25;
            v12 = (unsigned int)v9;
            goto LABEL_9;
          }
          goto LABEL_60;
        }
        RtlInitUnicodeString(&ValueName, L"TriggerEvent");
        v8 = BipReadRegGuid(KeyHandle, &ValueName, &Guid);
        v9 = v8;
        if ( v8 >= 0 )
        {
          if ( v23 )
          {
            if ( v23 != 1 )
            {
              v9 = -1073741811;
              goto LABEL_60;
            }
            v23 = 8;
            RtlInitUnicodeString(&ValueName, L"StateName");
            v8 = BipReadRegBinary(KeyHandle, &ValueName, &v32);
            v9 = v8;
            if ( v8 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v11 = 29;
                goto LABEL_8;
              }
              goto LABEL_60;
            }
            v16 = BiSrvAssociateActivationProxy(a2, &v32, 0, 137, v24, a2, &v32, 0, &Guid, v6, v7, p_UnicodeString);
            v9 = v16;
            if ( v16 >= 0 )
              goto LABEL_60;
            v17 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_60;
            v18 = 30;
          }
          else
          {
            RtlInitUnicodeString(&ValueName, L"TaskEntryPoint");
            v8 = BipReadRegUnicodeString(KeyHandle, &ValueName, &v28);
            v9 = v8;
            if ( v8 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v11 = 27;
                goto LABEL_8;
              }
              goto LABEL_60;
            }
            memset_0(&v35, 0, 0x80u);
            LODWORD(v21) = 0;
            LODWORD(v20) = 4;
            v34 = 32;
            *(GUID *)Buf1 = GUID_NULL;
            v16 = BiSrvAssociateApplicationEntryPoint(
                    a2,
                    0,
                    &v34,
                    0,
                    Buf1,
                    0x89u,
                    v24,
                    a2,
                    v28.Buffer,
                    v28.Length,
                    0,
                    0,
                    &Guid,
                    v6,
                    0,
                    v7,
                    p_UnicodeString,
                    v20,
                    0,
                    0,
                    v21,
                    0);
            v9 = v16;
            if ( v16 >= 0 )
              goto LABEL_60;
            v17 = WPP_GLOBAL_Control;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_60;
            v18 = 28;
          }
          WPP_SF__guid_d(v17[2], v18, WPP_b9992b7a0e48309012f383940558a5f4_Traceguids, a2, v16);
          goto LABEL_60;
        }
        v10 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 26;
          goto LABEL_8;
        }
      }
      else
      {
        v10 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 24;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 21;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 20;
LABEL_8:
      v12 = (unsigned int)v8;
LABEL_9:
      WPP_SF_d(v10[2], v11, WPP_b9992b7a0e48309012f383940558a5f4_Traceguids, v12);
    }
  }
LABEL_60:
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v6 )
    RtlFreeHeap(BipHeap, 0, v6);
  RtlFreeUnicodeString(&DestinationString);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v28);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180087cc4  mov     [rsp-8+arg_18], rbx
0x180087cc9  push    rbp
0x180087cca  push    rsi
0x180087ccb  push    rdi
0x180087ccc  push    r12
0x180087cce  push    r13
0x180087cd0  push    r14
0x180087cd2  push    r15
0x180087cd4  lea     rbp, [rsp-0E0h]
0x180087cdc  sub     rsp, 210h
0x180087ce3  mov     rax, cs:__security_cookie
0x180087cea  xor     rax, rsp
0x180087ced  mov     [rbp+110h+var_40], rax
0x180087cf4  xorps   xmm0, xmm0
0x180087cf7  xor     r12d, r12d
0x180087cfa  mov     r15, r8
0x180087cfd  mov     [rbp+110h+var_188], r12d
0x180087d01  mov     rsi, rdx
0x180087d04  mov     [rbp+110h+var_184], r12d
0x180087d08  mov     rbx, rcx
0x180087d0b  xorps   xmm1, xmm1
0x180087d0e  movups  xmmword ptr [rbp+110h+ObjectAttributes.ObjectName], xmm0
0x180087d12  xor     eax, eax
0x180087d14  lea     rcx, [rbp+110h+var_D0]; void *
0x180087d18  xor     edx, edx; Val
0x180087d1a  mov     r8d, 82h; Size
0x180087d20  movups  xmmword ptr [rbp+110h+ObjectAttributes+1Ch], xmm0
0x180087d24  movups  xmmword ptr [rbp+110h+DestinationString.Length], xmm0
0x180087d28  movups  xmmword ptr [rbp+110h+UnicodeString.Length], xmm1
0x180087d2c  movups  xmmword ptr [rbp+110h+ObjectAttributes.Length], xmm0
0x180087d30  call    memset_0
0x180087d35  xorps   xmm0, xmm0
0x180087d38  mov     [rbp+110h+var_F0], r12
0x180087d3c  xorps   xmm1, xmm1
0x180087d3f  mov     [rbp+110h+KeyHandle], r12
0x180087d43  movups  xmmword ptr [rbp+110h+var_150.Length], xmm0
0x180087d47  movups  xmmword ptr [rbp+110h+Guid.Data1], xmm1
0x180087d4b  movups  xmmword ptr [rbp+110h+ValueName.Length], xmm0
0x180087d4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087d56  lea     r13d, [r12+8]
0x180087d5b  test    [rcx+1Ch], r13b
0x180087d5f  jz      short loc_180087D7F
0x180087d61  cmp     byte ptr [rcx+19h], 4
0x180087d65  jb      short loc_180087D7F
0x180087d67  mov     rcx, [rcx+10h]
0x180087d6b  lea     edx, [r12+13h]
0x180087d70  mov     r9, rsi
0x180087d73  lea     r8, WPP_b9992b7a0e48309012f383940558a5f4_Traceguids
0x180087d7a  call    WPP_SF__guid_
0x180087d7f  xor     edx, edx; SourceString
0x180087d81  lea     rcx, [rbp+110h+DestinationString]; DestinationString
0x180087d85  call    cs:__imp_RtlInitUnicodeString
0x180087d8b  xor     edx, edx; SourceString
0x180087d8d  lea     rcx, [rbp+110h+UnicodeString]; DestinationString
0x180087d91  call    cs:__imp_RtlInitUnicodeString
0x180087d97  xor     edx, edx; SourceString
0x180087d99  lea     rcx, [rbp+110h+var_150]; DestinationString
0x180087d9d  call    cs:__imp_RtlInitUnicodeString
0x180087da3  xorps   xmm0, xmm0
0x180087da6  mov     [rbp+110h+KeyHandle], r12
0x180087daa  lea     r8, [rbp+110h+ObjectAttributes]; ObjectAttributes
0x180087dae  mov     [rbp+110h+var_160], r12
0x180087db2  mov     edx, 0F003Fh; DesiredAccess
0x180087db7  mov     [rbp+110h+var_170], r12d
0x180087dbb  lea     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x180087dbf  mov     [rbp+110h+ObjectAttributes.Length], 30h ; '0'
0x180087dc6  movdqu  xmmword ptr [rbp+110h+ObjectAttributes.SecurityDescriptor], xmm0
0x180087dcb  mov     rdi, r12
0x180087dce  mov     [rbp+110h+ObjectAttributes.RootDirectory], rbx
0x180087dd2  mov     r14d, r12d
0x180087dd5  mov     [rbp+110h+ObjectAttributes.Attributes], 40h ; '@'
0x180087ddc  mov     [rbp+110h+ObjectAttributes.ObjectName], r15
0x180087de0  call    cs:__imp_NtOpenKey
0x180087de6  mov     ebx, eax
0x180087de8  test    eax, eax
0x180087dea  jns     short loc_180087E24
0x180087dec  mov     rcx, cs:WPP_GLOBAL_Control
0x180087df3  test    [rcx+1Ch], r13b
0x180087df7  jz      loc_18008823C
0x180087dfd  cmp     byte ptr [rcx+19h], 2
0x180087e01  jb      loc_18008823C
0x180087e07  mov     edx, 14h
0x180087e0c  mov     r9d, eax
0x180087e0f  mov     rcx, [rcx+10h]
0x180087e13  lea     r8, WPP_b9992b7a0e48309012f383940558a5f4_Traceguids
0x180087e1a  call    WPP_SF_d
0x180087e1f  jmp     loc_18008823C
0x180087e24  lea     rdx, aActivationtype; "ActivationType"
0x180087e2b  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x180087e2f  call    cs:__imp_RtlInitUnicodeString
0x180087e35  mov     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x180087e39  lea     r8, [rbp+110h+var_188]
0x180087e3d  lea     rdx, [rbp+110h+ValueName]; ValueName
0x180087e41  call    BipReadRegUlong
0x180087e46  mov     ebx, eax
0x180087e48  test    eax, eax
0x180087e4a  jns     short loc_180087E6E
0x180087e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087e53  test    [rcx+1Ch], r13b
0x180087e57  jz      loc_18008823C
0x180087e5d  cmp     byte ptr [rcx+19h], 2
0x180087e61  jb      loc_18008823C
0x180087e67  mov     edx, 15h
0x180087e6c  jmp     short loc_180087E0C
0x180087e6e  lea     rdx, aConditions; "Conditions"
0x180087e75  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x180087e79  call    cs:__imp_RtlInitUnicodeString
0x180087e7f  mov     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x180087e83  lea     r8, [rbp+110h+DestinationString]; DestinationString
0x180087e87  lea     rdx, [rbp+110h+ValueName]; ValueName
0x180087e8b  call    BipReadRegMultiSz
0x180087e90  mov     ebx, eax
0x180087e92  mov     r15d, 0C0000034h
0x180087e98  test    eax, eax
0x180087e9a  js      loc_180087F40
0x180087ea0  lea     r8, [rbp+110h+var_160]
0x180087ea4  lea     rdx, [rbp+110h+var_170]
0x180087ea8  lea     rcx, [rbp+110h+DestinationString]
0x180087eac  call    BipParseConditionString
0x180087eb1  mov     ebx, eax
0x180087eb3  test    eax, eax
0x180087eb5  jns     short loc_180087EEB
0x180087eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ebe  test    [rcx+1Ch], r13b
0x180087ec2  jz      short loc_180087EE2
0x180087ec4  cmp     byte ptr [rcx+19h], 2
0x180087ec8  jb      short loc_180087EE2
0x180087eca  mov     rcx, [rcx+10h]
0x180087ece  lea     r8, WPP_b9992b7a0e48309012f383940558a5f4_Traceguids
0x180087ed5  mov     edx, 16h
0x180087eda  mov     r9d, eax
0x180087edd  call    WPP_SF_d
0x180087ee2  mov     rdi, [rbp+110h+var_160]
0x180087ee6  jmp     loc_18008823C
0x180087eeb  mov     r14d, [rbp+110h+var_170]
0x180087eef  mov     rdi, [rbp+110h+var_160]
0x180087ef3  lea     rdx, aFlags; "Flags"
0x180087efa  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x180087efe  call    cs:__imp_RtlInitUnicodeString
0x180087f04  mov     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x180087f08  lea     r8, [rbp+110h+var_184]
0x180087f0c  lea     rdx, [rbp+110h+ValueName]; ValueName
0x180087f10  call    BipReadRegUlong
0x180087f15  mov     ebx, eax
0x180087f17  test    eax, eax
0x180087f19  jns     short loc_180087F6A
0x180087f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180087f22  test    [rcx+1Ch], r13b
0x180087f26  jz      loc_18008823C
0x180087f2c  cmp     byte ptr [rcx+19h], 2
0x180087f30  jb      loc_18008823C
0x180087f36  mov     edx, 18h
0x180087f3b  jmp     loc_180087E0C
0x180087f40  cmp     eax, r15d
0x180087f43  jz      short loc_180087EF3
0x180087f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180087f4c  test    [rcx+1Ch], r13b
0x180087f50  jz      loc_18008823C
0x180087f56  cmp     byte ptr [rcx+19h], 2
0x180087f5a  jb      loc_18008823C
0x180087f60  mov     edx, 17h
0x180087f65  jmp     loc_180087E0C
0x180087f6a  lea     rdx, aName; "Name"
0x180087f71  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x180087f75  call    cs:__imp_RtlInitUnicodeString
0x180087f7b  mov     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x180087f7f  lea     r8, [rbp+110h+UnicodeString]; DestinationString
0x180087f83  lea     rdx, [rbp+110h+ValueName]; ValueName
0x180087f87  call    BipReadRegUnicodeString
0x180087f8c  cmp     eax, r15d
0x180087f8f  mov     ebx, r12d
0x180087f92  lea     r15, [rbp+110h+UnicodeString]
0x180087f96  cmovnz  ebx, eax
0x180087f99  cmp     eax, 0C0000034h
0x180087f9e  cmovz   r15, r12
0x180087fa2  test    ebx, ebx
0x180087fa4  jns     short loc_180087FCE
0x180087fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180087fad  test    [rcx+1Ch], r13b
0x180087fb1  jz      loc_18008823C
0x180087fb7  cmp     byte ptr [rcx+19h], 2
0x180087fbb  jb      loc_18008823C
0x180087fc1  mov     edx, 19h
0x180087fc6  mov     r9d, ebx
0x180087fc9  jmp     loc_180087E0F
0x180087fce  lea     rdx, aTriggerevent; "TriggerEvent"
0x180087fd5  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x180087fd9  call    cs:__imp_RtlInitUnicodeString
0x180087fdf  mov     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x180087fe3  lea     r8, [rbp+110h+Guid]; Guid
0x180087fe7  lea     rdx, [rbp+110h+ValueName]; ValueName
0x180087feb  call    BipReadRegGuid
0x180087ff0  mov     ebx, eax
0x180087ff2  test    eax, eax
0x180087ff4  jns     short loc_18008801B
0x180087ff6  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ffd  test    [rcx+1Ch], r13b
0x180088001  jz      loc_18008823C
0x180088007  cmp     byte ptr [rcx+19h], 2
0x18008800b  jb      loc_18008823C
0x180088011  mov     edx, 1Ah
0x180088016  jmp     loc_180087E0C
0x18008801b  mov     ecx, [rbp+110h+var_188]
0x18008801e  test    ecx, ecx
0x180088020  jz      loc_180088100
0x180088026  cmp     ecx, 1
0x180088029  jz      short loc_180088035
0x18008802b  mov     ebx, 0C000000Dh
0x180088030  jmp     loc_18008823C
0x180088035  lea     rdx, aStatename; "StateName"
0x18008803c  mov     [rbp+110h+var_188], r13d
0x180088040  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x180088044  call    cs:__imp_RtlInitUnicodeString
0x18008804a  mov     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x18008804e  lea     r9, [rbp+110h+var_188]
0x180088052  lea     r8, [rbp+110h+var_F0]; void *
0x180088056  lea     rdx, [rbp+110h+ValueName]; ValueName
0x18008805a  call    BipReadRegBinary
0x18008805f  mov     ebx, eax
0x180088061  test    eax, eax
0x180088063  jns     short loc_18008808A
0x180088065  mov     rcx, cs:WPP_GLOBAL_Control
0x18008806c  test    [rcx+1Ch], r13b
0x180088070  jz      loc_18008823C
0x180088076  cmp     byte ptr [rcx+19h], 2
0x18008807a  jb      loc_18008823C
0x180088080  mov     edx, 1Dh
0x180088085  jmp     loc_180087E0C
0x18008808a  mov     qword ptr [rsp+240h+var_1E8], r15
0x18008808f  lea     rax, [rbp+110h+Guid]
0x180088093  mov     dword ptr [rsp+240h+var_1F0], r14d
0x180088098  lea     rdx, [rbp+110h+var_F0]
0x18008809c  mov     qword ptr [rsp+240h+var_1F8], rdi
0x1800880a1  mov     r9d, 89h
0x1800880a7  mov     [rsp+240h+var_200], rax
0x1800880ac  xor     r8d, r8d
0x1800880af  lea     rax, [rbp+110h+var_F0]
0x1800880b3  mov     [rsp+240h+var_208], r12
0x1800880b8  mov     qword ptr [rsp+240h+var_210], rax
0x1800880bd  mov     rcx, rsi
0x1800880c0  mov     eax, [rbp+110h+var_184]
0x1800880c3  mov     qword ptr [rsp+240h+var_218], rsi
0x1800880c8  mov     dword ptr [rsp+240h+Buf1], eax
0x1800880cc  call    BiSrvAssociateActivationProxy
0x1800880d1  mov     ebx, eax
0x1800880d3  test    eax, eax
0x1800880d5  jns     loc_18008823C
0x1800880db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800880e2  test    [rcx+1Ch], r13b
0x1800880e6  jz      loc_18008823C
0x1800880ec  cmp     byte ptr [rcx+19h], 2
0x1800880f0  jb      loc_18008823C
0x1800880f6  mov     edx, 1Eh
0x1800880fb  jmp     loc_180088225
0x180088100  lea     rdx, aTaskentrypoint_0; "TaskEntryPoint"
0x180088107  lea     rcx, [rbp+110h+ValueName]; DestinationString
0x18008810b  call    cs:__imp_RtlInitUnicodeString
0x180088111  mov     rcx, [rbp+110h+KeyHandle]; KeyHandle
0x180088115  lea     r8, [rbp+110h+var_150]; DestinationString
0x180088119  lea     rdx, [rbp+110h+ValueName]; ValueName
0x18008811d  call    BipReadRegUnicodeString
0x180088122  mov     ebx, eax
0x180088124  test    eax, eax
0x180088126  jns     short loc_18008814D
0x180088128  mov     rcx, cs:WPP_GLOBAL_Control
0x18008812f  test    [rcx+1Ch], r13b
0x180088133  jz      loc_18008823C
0x180088139  cmp     byte ptr [rcx+19h], 2
0x18008813d  jb      loc_18008823C
0x180088143  mov     edx, 1Bh
0x180088148  jmp     loc_180087E0C
0x18008814d  xor     edx, edx; Val
0x18008814f  lea     rcx, [rbp+110h+var_D0+2]; void *
0x180088153  mov     r8d, 80h; Size
0x180088159  call    memset_0
0x18008815e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180088165  mov     [rsp+240h+var_198], r12; __int64
0x18008816d  lea     rcx, [rbp+110h+Guid]
0x180088171  mov     dword ptr [rsp+240h+var_1A0], r12d; size_t
0x180088179  lea     r8, [rbp+110h+var_D0]; int
0x18008817d  mov     [rsp+240h+var_1A8], r12; __int64
0x180088185  mov     eax, 20h ; ' '
0x18008818a  mov     [rsp+240h+var_1B0], r12d; int
0x180088192  xor     r9d, r9d; int
0x180088195  mov     dword ptr [rsp+240h+var_1B8], 4; __int64
0x1800881a0  xor     edx, edx; int
0x1800881a2  mov     [rsp+240h+var_1C0], r15; __int64
0x1800881aa  mov     [rsp+240h+var_1C8], r14d; unsigned int
0x1800881af  mov     [rsp+240h+var_1D0], r12; __int64
0x1800881b4  mov     [rsp+240h+var_1D8], rdi; __int64
0x1800881b9  mov     [rsp+240h+var_1E0], rcx; __int64
0x1800881be  mov     rcx, rsi; int
0x1800881c1  mov     [rsp+240h+var_1E8], r12d; int
0x1800881c6  mov     [rsp+240h+var_1F0], r12; __int64
0x1800881cb  mov     word ptr [rbp+110h+var_D0], ax
0x1800881cf  movzx   eax, [rbp+110h+var_150.Length]
0x1800881d3  mov     [rsp+240h+var_1F8], eax; int
0x1800881d7  mov     rax, [rbp+110h+var_150.Buffer]
0x1800881db  mov     [rsp+240h+var_200], rax; __int64
0x1800881e0  mov     eax, [rbp+110h+var_184]
  ... truncated ...
```

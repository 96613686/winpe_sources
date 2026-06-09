# BipUpdateEventUserSidInStore

- ea: `0x1800845c0`
- end: `0x18008472c`
- name: `BipUpdateEventUserSidInStore`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005df20`

## callees

- `0x1800249ec`
- `0x180024e14`
- `0x180049844`
- `0x1800845c0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180084675`
- `ntdll!NtOpenKey` at `0x180084675`
- `ntdll!RtlInitUnicodeString` at `0x1800846a6`
- `ntdll!RtlInitUnicodeString` at `0x1800846a6`
- `ntdll!RtlFreeHeap` at `0x180084703`
- `ntdll!RtlFreeHeap` at `0x180084703`
- `ntdll!NtClose` at `0x180084712`
- `ntdll!NtClose` at `0x180084712`

## string_xrefs

- `0x18008469b`: `UserSid`

## pseudocode

```c
__int64 __fastcall BipUpdateEventUserSidInStore(__int64 a1)
{
  bool v1; // zf
  unsigned int v3; // ebx
  NTSTATUS v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  PVOID P[2]; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+10h] BYREF

  v1 = *(_QWORD *)(a1 + 168) == 0;
  KeyHandle = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( v1 )
  {
    v3 = -1073741811;
    goto LABEL_16;
  }
  v4 = BipConstructEventKeyName(a1, P);
  v3 = v4;
  if ( v4 >= 0 )
  {
    ObjectAttributes.RootDirectory = ::KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
    v3 = v4;
    if ( v4 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"UserSid");
      v4 = BipWriteRegSid(KeyHandle, &DestinationString, *(PVOID *)(a1 + 168));
      v3 = v4;
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 81;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 80;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 79;
LABEL_15:
      WPP_SF_d(v5[2], v6, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids, (unsigned int)v4);
    }
  }
LABEL_16:
  if ( P[1] )
    RtlFreeHeap(BipHeap, 0, P[1]);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v3;
}

```

## disassembly

```asm
0x1800845c0  mov     [rsp-8+arg_8], rbx
0x1800845c5  mov     [rsp-8+arg_10], rdi
0x1800845ca  push    rbp
0x1800845cb  mov     rbp, rsp
0x1800845ce  sub     rsp, 70h
0x1800845d2  cmp     qword ptr [rcx+0A8h], 0
0x1800845da  xorps   xmm1, xmm1
0x1800845dd  xorps   xmm0, xmm0
0x1800845e0  mov     [rbp+KeyHandle], 0
0x1800845e8  movups  xmmword ptr [rbp+P], xmm0
0x1800845ec  mov     rdi, rcx
0x1800845ef  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800845f3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800845f7  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800845fb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800845ff  jnz     short loc_18008460B
0x180084601  mov     ebx, 0C000000Dh
0x180084606  jmp     loc_1800846F1
0x18008460b  lea     rdx, [rbp+P]
0x18008460f  call    BipConstructEventKeyName
0x180084614  mov     ebx, eax
0x180084616  test    eax, eax
0x180084618  jns     short loc_18008463F
0x18008461a  mov     rcx, cs:WPP_GLOBAL_Control
0x180084621  test    byte ptr [rcx+1Ch], 8
0x180084625  jz      loc_1800846F1
0x18008462b  cmp     byte ptr [rcx+19h], 2
0x18008462f  jb      loc_1800846F1
0x180084635  mov     edx, 4Fh ; 'O'
0x18008463a  jmp     loc_1800846DE
0x18008463f  mov     rax, cs:KeyHandle
0x180084646  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18008464a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18008464e  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180084652  lea     rax, [rbp+P]
0x180084656  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18008465d  xorps   xmm0, xmm0
0x180084660  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180084664  mov     edx, 0F003Fh; DesiredAccess
0x180084669  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180084670  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180084675  call    cs:__imp_NtOpenKey
0x18008467b  mov     ebx, eax
0x18008467d  test    eax, eax
0x18008467f  jns     short loc_18008469B
0x180084681  mov     rcx, cs:WPP_GLOBAL_Control
0x180084688  test    byte ptr [rcx+1Ch], 8
0x18008468c  jz      short loc_1800846F1
0x18008468e  cmp     byte ptr [rcx+19h], 2
0x180084692  jb      short loc_1800846F1
0x180084694  mov     edx, 50h ; 'P'
0x180084699  jmp     short loc_1800846DE
0x18008469b  lea     rdx, aUsersid; "UserSid"
0x1800846a2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800846a6  call    cs:__imp_RtlInitUnicodeString
0x1800846ac  mov     r8, [rdi+0A8h]; Data
0x1800846b3  lea     rdx, [rbp+DestinationString]; ValueName
0x1800846b7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800846bb  call    BipWriteRegSid
0x1800846c0  mov     ebx, eax
0x1800846c2  test    eax, eax
0x1800846c4  jns     short loc_1800846F1
0x1800846c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800846cd  test    byte ptr [rcx+1Ch], 8
0x1800846d1  jz      short loc_1800846F1
0x1800846d3  cmp     byte ptr [rcx+19h], 2
0x1800846d7  jb      short loc_1800846F1
0x1800846d9  mov     edx, 51h ; 'Q'
0x1800846de  mov     rcx, [rcx+10h]
0x1800846e2  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x1800846e9  mov     r9d, eax
0x1800846ec  call    WPP_SF_d
0x1800846f1  mov     r8, [rbp+P+8]; P
0x1800846f5  test    r8, r8
0x1800846f8  jz      short loc_180084709
0x1800846fa  mov     rcx, cs:BipHeap; HeapHandle
0x180084701  xor     edx, edx; Flags
0x180084703  call    cs:__imp_RtlFreeHeap
0x180084709  mov     rcx, [rbp+KeyHandle]; Handle
0x18008470d  test    rcx, rcx
0x180084710  jz      short loc_180084718
0x180084712  call    cs:__imp_NtClose
0x180084718  lea     r11, [rsp+70h+var_s0]
0x18008471d  mov     eax, ebx
0x18008471f  mov     rbx, [r11+18h]
0x180084723  mov     rdi, [r11+20h]
0x180084727  mov     rsp, r11
0x18008472a  pop     rbp
0x18008472b  retn
```

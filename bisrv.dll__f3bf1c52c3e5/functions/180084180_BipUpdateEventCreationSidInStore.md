# BipUpdateEventCreationSidInStore

- ea: `0x180084180`
- end: `0x1800842ec`
- name: `BipUpdateEventCreationSidInStore`
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
- `0x180084180`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180084235`
- `ntdll!NtOpenKey` at `0x180084235`
- `ntdll!RtlInitUnicodeString` at `0x180084266`
- `ntdll!RtlInitUnicodeString` at `0x180084266`
- `ntdll!RtlFreeHeap` at `0x1800842c3`
- `ntdll!RtlFreeHeap` at `0x1800842c3`
- `ntdll!NtClose` at `0x1800842d2`
- `ntdll!NtClose` at `0x1800842d2`

## string_xrefs

- `0x18008425b`: `CreationSid`

## pseudocode

```c
__int64 __fastcall BipUpdateEventCreationSidInStore(__int64 a1)
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

  v1 = *(_QWORD *)(a1 + 184) == 0;
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
      RtlInitUnicodeString(&DestinationString, L"CreationSid");
      v4 = BipWriteRegSid(KeyHandle, &DestinationString, *(PVOID *)(a1 + 184));
      v3 = v4;
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 66;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 65;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 64;
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
0x180084180  mov     [rsp-8+arg_8], rbx
0x180084185  mov     [rsp-8+arg_10], rdi
0x18008418a  push    rbp
0x18008418b  mov     rbp, rsp
0x18008418e  sub     rsp, 70h
0x180084192  cmp     qword ptr [rcx+0B8h], 0
0x18008419a  xorps   xmm1, xmm1
0x18008419d  xorps   xmm0, xmm0
0x1800841a0  mov     [rbp+KeyHandle], 0
0x1800841a8  movups  xmmword ptr [rbp+P], xmm0
0x1800841ac  mov     rdi, rcx
0x1800841af  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1800841b3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1800841b7  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1800841bb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800841bf  jnz     short loc_1800841CB
0x1800841c1  mov     ebx, 0C000000Dh
0x1800841c6  jmp     loc_1800842B1
0x1800841cb  lea     rdx, [rbp+P]
0x1800841cf  call    BipConstructEventKeyName
0x1800841d4  mov     ebx, eax
0x1800841d6  test    eax, eax
0x1800841d8  jns     short loc_1800841FF
0x1800841da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800841e1  test    byte ptr [rcx+1Ch], 8
0x1800841e5  jz      loc_1800842B1
0x1800841eb  cmp     byte ptr [rcx+19h], 2
0x1800841ef  jb      loc_1800842B1
0x1800841f5  mov     edx, 40h ; '@'
0x1800841fa  jmp     loc_18008429E
0x1800841ff  mov     rax, cs:KeyHandle
0x180084206  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18008420a  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x18008420e  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180084212  lea     rax, [rbp+P]
0x180084216  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18008421d  xorps   xmm0, xmm0
0x180084220  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180084224  mov     edx, 0F003Fh; DesiredAccess
0x180084229  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180084230  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180084235  call    cs:__imp_NtOpenKey
0x18008423b  mov     ebx, eax
0x18008423d  test    eax, eax
0x18008423f  jns     short loc_18008425B
0x180084241  mov     rcx, cs:WPP_GLOBAL_Control
0x180084248  test    byte ptr [rcx+1Ch], 8
0x18008424c  jz      short loc_1800842B1
0x18008424e  cmp     byte ptr [rcx+19h], 2
0x180084252  jb      short loc_1800842B1
0x180084254  mov     edx, 41h ; 'A'
0x180084259  jmp     short loc_18008429E
0x18008425b  lea     rdx, aCreationsid; "CreationSid"
0x180084262  lea     rcx, [rbp+DestinationString]; DestinationString
0x180084266  call    cs:__imp_RtlInitUnicodeString
0x18008426c  mov     r8, [rdi+0B8h]; Data
0x180084273  lea     rdx, [rbp+DestinationString]; ValueName
0x180084277  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18008427b  call    BipWriteRegSid
0x180084280  mov     ebx, eax
0x180084282  test    eax, eax
0x180084284  jns     short loc_1800842B1
0x180084286  mov     rcx, cs:WPP_GLOBAL_Control
0x18008428d  test    byte ptr [rcx+1Ch], 8
0x180084291  jz      short loc_1800842B1
0x180084293  cmp     byte ptr [rcx+19h], 2
0x180084297  jb      short loc_1800842B1
0x180084299  mov     edx, 42h ; 'B'
0x18008429e  mov     rcx, [rcx+10h]
0x1800842a2  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x1800842a9  mov     r9d, eax
0x1800842ac  call    WPP_SF_d
0x1800842b1  mov     r8, [rbp+P+8]; P
0x1800842b5  test    r8, r8
0x1800842b8  jz      short loc_1800842C9
0x1800842ba  mov     rcx, cs:BipHeap; HeapHandle
0x1800842c1  xor     edx, edx; Flags
0x1800842c3  call    cs:__imp_RtlFreeHeap
0x1800842c9  mov     rcx, [rbp+KeyHandle]; Handle
0x1800842cd  test    rcx, rcx
0x1800842d0  jz      short loc_1800842D8
0x1800842d2  call    cs:__imp_NtClose
0x1800842d8  lea     r11, [rsp+70h+var_s0]
0x1800842dd  mov     eax, ebx
0x1800842df  mov     rbx, [r11+18h]
0x1800842e3  mov     rdi, [r11+20h]
0x1800842e7  mov     rsp, r11
0x1800842ea  pop     rbp
0x1800842eb  retn
```

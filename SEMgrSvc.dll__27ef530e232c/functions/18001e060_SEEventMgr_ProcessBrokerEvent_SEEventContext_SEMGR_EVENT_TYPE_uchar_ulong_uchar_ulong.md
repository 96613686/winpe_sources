# SEEventMgr::ProcessBrokerEvent(SEEventContext *,SEMGR_EVENT_TYPE,uchar *,ulong,uchar *,ulong)

- ea: `0x18001e060`
- end: `0x18001e24a`
- name: `?ProcessBrokerEvent@SEEventMgr@@AEAA_NPEAUSEEventContext@@W4SEMGR_EVENT_TYPE@@PEAEK2K@Z`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e3f4`

## callees

- `0x1800049a0`
- `0x1800057c6`
- `0x180005858`
- `0x18000ea58`
- `0x18001e060`
- `0x180097150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e145`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e175`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e145`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e175`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e0cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e0cb`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001e1d8`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001e201`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001e1d8`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18001e201`

## pseudocode

```c
bool __fastcall SEEventMgr::ProcessBrokerEvent(
        __int64 a1,
        __int64 *a2,
        unsigned int a3,
        const void *a4,
        unsigned int SourceSize,
        void *a6,
        unsigned int a7)
{
  char v7; // di
  int v11; // eax
  _BYTE *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // esi
  size_t v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned int v21; // esi
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // eax
  bool v25; // sf
  signed int v26; // eax
  int v28; // [rsp+30h] [rbp-1068h] BYREF
  __int64 v29; // [rsp+38h] [rbp-1060h]
  void *Source; // [rsp+40h] [rbp-1058h]
  _DWORD v31[2]; // [rsp+50h] [rbp-1048h] BYREF
  _BYTE Destination[4088]; // [rsp+58h] [rbp-1040h] BYREF

  v7 = 0;
  v29 = a1;
  Source = a6;
  LOBYTE(v28) = 0;
  if ( !*((_BYTE *)a2 + 24) )
    return v7;
  a2[2] = GetTickCount64();
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1u:
        v11 = 2;
        break;
      case 2u:
        v11 = 0;
        break;
      case 3u:
        v11 = 3;
        break;
      case 4u:
        v11 = 4;
        break;
      default:
        return v7;
    }
  }
  else
  {
    v11 = 1;
  }
  v31[0] = v11;
  v31[1] = SourceSize;
  v12 = Destination;
  if ( SourceSize )
  {
    v12 = &Destination[SourceSize];
    memcpy_s(Destination, 0xFF8u, a4, SourceSize);
    v16 = SourceSize + 8;
    if ( !v12 )
    {
      *(_DWORD *)_o__errno(v14, v13, v15) = 22;
LABEL_19:
      invalid_parameter_noinfo();
      goto LABEL_20;
    }
  }
  else
  {
    v16 = 8;
  }
  v17 = 4096LL - v16;
  if ( v17 < 4 )
  {
    memset_0(v12, 0, v17);
    *(_DWORD *)_o__errno(v19, v18, v20) = 34;
    goto LABEL_19;
  }
  *(_DWORD *)v12 = a7;
LABEL_20:
  v21 = v16 + 4;
  if ( a7 )
  {
    memcpy_s(v12 + 4, 4096LL - v21, Source, a7);
    v21 += a7;
  }
  v22 = *a2;
  v23 = *(_QWORD *)(v29 + 88);
  if ( a3 <= 1 )
  {
    LOBYTE(v28) = a3 == *((_DWORD *)a2 + 2);
    v26 = ((__int64 (__fastcall *)(__int64, __int64, int *, GUID *, unsigned int, _DWORD *))BrSignalBrokerEvent2)(
            v23,
            v22,
            &v28,
            &CLSID_SmartCardTriggerDetailsFactory,
            v21,
            v31);
    if ( v26 > 0 )
      v26 = (unsigned __int16)v26 | 0x80070000;
    return v26 >= 0;
  }
  else
  {
    v24 = BrSignalBrokerEvent2(v23, v22, 0, &CLSID_SmartCardTriggerDetailsFactory, v21, v31, v28);
    v25 = v24 < 0;
    if ( v24 > 0 )
      v25 = 1;
    if ( !v25 )
      return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18001e060  mov     [rsp+arg_10], rbx
0x18001e065  push    rbp
0x18001e066  push    rsi
0x18001e067  push    rdi
0x18001e068  push    r12
0x18001e06a  push    r13
0x18001e06c  push    r14
0x18001e06e  push    r15
0x18001e070  mov     eax, 1060h
0x18001e075  call    _alloca_probe
0x18001e07a  sub     rsp, rax
0x18001e07d  mov     rax, cs:__security_cookie
0x18001e084  xor     rax, rsp
0x18001e087  mov     [rsp+1098h+var_48], rax
0x18001e08f  mov     rax, [rsp+1098h+arg_28]
0x18001e097  xor     dil, dil
0x18001e09a  mov     r13, r9
0x18001e09d  mov     esi, dword ptr [rsp+1098h+SourceSize]
0x18001e0a4  mov     r14d, r8d
0x18001e0a7  mov     r12d, dword ptr [rsp+1098h+arg_30]
0x18001e0af  mov     r15, rdx
0x18001e0b2  mov     [rsp+1098h+var_1060], rcx
0x18001e0b7  mov     [rsp+1098h+Source], rax
0x18001e0bc  mov     byte ptr [rsp+1098h+var_1068], 0
0x18001e0c1  cmp     [rdx+18h], dil
0x18001e0c5  jz      loc_18001E21C
0x18001e0cb  call    cs:__imp_GetTickCount64
0x18001e0d1  mov     [r15+10h], rax
0x18001e0d5  mov     ecx, r14d
0x18001e0d8  test    r14d, r14d
0x18001e0db  jz      short loc_18001E10C
0x18001e0dd  sub     ecx, 1
0x18001e0e0  jz      short loc_18001E105
0x18001e0e2  sub     ecx, 1
0x18001e0e5  jz      short loc_18001E101
0x18001e0e7  sub     ecx, 1
0x18001e0ea  jz      short loc_18001E0FA
0x18001e0ec  cmp     ecx, 1
0x18001e0ef  jnz     loc_18001E21C
0x18001e0f5  lea     eax, [rcx+3]
0x18001e0f8  jmp     short loc_18001E111
0x18001e0fa  mov     eax, 3
0x18001e0ff  jmp     short loc_18001E111
0x18001e101  xor     eax, eax
0x18001e103  jmp     short loc_18001E111
0x18001e105  mov     eax, 2
0x18001e10a  jmp     short loc_18001E111
0x18001e10c  mov     eax, 1
0x18001e111  mov     [rsp+1098h+var_1048], eax
0x18001e115  mov     ebp, 1000h
0x18001e11a  mov     [rsp+1098h+var_1044], esi
0x18001e11e  lea     rbx, [rsp+1098h+Destination]
0x18001e123  test    esi, esi
0x18001e125  jz      short loc_18001E153
0x18001e127  mov     r9, rsi; SourceSize
0x18001e12a  lea     edx, [rbp-8]; DestinationSize
0x18001e12d  mov     r8, r13; Source
0x18001e130  lea     rcx, [rsp+1098h+Destination]; Destination
0x18001e135  add     rbx, rsi
0x18001e138  call    memcpy_s
0x18001e13d  add     esi, 8
0x18001e140  test    rbx, rbx
0x18001e143  jnz     short loc_18001E158
0x18001e145  call    cs:__imp__o__errno
0x18001e14b  mov     dword ptr [rax], 16h
0x18001e151  jmp     short loc_18001E181
0x18001e153  mov     esi, 8
0x18001e158  mov     eax, esi
0x18001e15a  mov     r8, rbp
0x18001e15d  sub     r8, rax; Size
0x18001e160  cmp     r8, 4
0x18001e164  jb      short loc_18001E16B
0x18001e166  mov     [rbx], r12d
0x18001e169  jmp     short loc_18001E186
0x18001e16b  xor     edx, edx; Val
0x18001e16d  mov     rcx, rbx; void *
0x18001e170  call    memset_0
0x18001e175  call    cs:__imp__o__errno
0x18001e17b  mov     dword ptr [rax], 22h ; '"'
0x18001e181  call    _invalid_parameter_noinfo
0x18001e186  add     esi, 4
0x18001e189  test    r12d, r12d
0x18001e18c  jz      short loc_18001E1AA
0x18001e18e  mov     r8, [rsp+1098h+Source]; Source
0x18001e193  lea     rcx, [rbx+4]; Destination
0x18001e197  mov     eax, esi
0x18001e199  mov     r9, r12; SourceSize
0x18001e19c  sub     rbp, rax
0x18001e19f  mov     rdx, rbp; DestinationSize
0x18001e1a2  call    memcpy_s
0x18001e1a7  add     esi, r12d
0x18001e1aa  mov     rcx, [rsp+1098h+var_1060]
0x18001e1af  lea     rax, [rsp+1098h+var_1048]
0x18001e1b4  mov     rdx, [r15]
0x18001e1b7  lea     r9, ?CLSID_SmartCardTriggerDetailsFactory@@3U_GUID@@B; _GUID const CLSID_SmartCardTriggerDetailsFactory
0x18001e1be  mov     ebx, 1
0x18001e1c3  mov     [rsp+1098h+var_1070], rax
0x18001e1c8  mov     [rsp+1098h+var_1078], esi
0x18001e1cc  mov     rcx, [rcx+58h]
0x18001e1d0  cmp     r14d, ebx
0x18001e1d3  jbe     short loc_18001E1F3
0x18001e1d5  xor     r8d, r8d
0x18001e1d8  call    cs:__imp_BrSignalBrokerEvent2
0x18001e1de  test    eax, eax
0x18001e1e0  jle     short loc_18001E1EC
0x18001e1e2  movzx   eax, ax
0x18001e1e5  or      eax, 80070000h
0x18001e1ea  test    eax, eax
0x18001e1ec  js      short loc_18001E21C
0x18001e1ee  mov     dil, bl
0x18001e1f1  jmp     short loc_18001E21C
0x18001e1f3  cmp     r14d, [r15+8]
0x18001e1f7  lea     r8, [rsp+1098h+var_1068]
0x18001e1fc  setz    byte ptr [rsp+1098h+var_1068]
0x18001e201  call    cs:__imp_BrSignalBrokerEvent2
0x18001e207  test    eax, eax
0x18001e209  jle     short loc_18001E213
0x18001e20b  movzx   eax, ax
0x18001e20e  or      eax, 80070000h
0x18001e213  test    eax, eax
0x18001e215  movzx   edi, dil
0x18001e219  cmovns  edi, ebx
0x18001e21c  mov     al, dil
0x18001e21f  mov     rcx, [rsp+1098h+var_48]
0x18001e227  xor     rcx, rsp; StackCookie
0x18001e22a  call    __security_check_cookie
0x18001e22f  mov     rbx, [rsp+1098h+arg_10]
0x18001e237  add     rsp, 1060h
0x18001e23e  pop     r15
0x18001e240  pop     r14
0x18001e242  pop     r13
0x18001e244  pop     r12
0x18001e246  pop     rdi
0x18001e247  pop     rsi
0x18001e248  pop     rbp
0x18001e249  retn
```

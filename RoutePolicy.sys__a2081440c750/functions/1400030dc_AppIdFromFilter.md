# AppIdFromFilter

- ea: `0x1400030dc`
- end: `0x140003338`
- name: `AppIdFromFilter`
- size: `604`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003340`
- `0x1400037a4`
- `0x140004330`
- `0x140004a84`

## callees

- `0x140001008`
- `0x140001bfc`
- `0x1400030dc`
- `0x14000935c`
- `0x14000a780`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400031fc`
- `ntoskrnl!ExAllocatePool2` at `0x1400031fc`

## string_xrefs

- `0x1400032c0`: `RoutePolicyCache::AppIdFromPackageId failed`

## pseudocode

```c
__int64 __fastcall AppIdFromFilter(__int64 a1, __int16 a2, unsigned __int16 **a3, RoutePolicyCache *a4)
{
  unsigned int v5; // ebx
  const char **v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rdx
  __int64 v10; // rcx
  const void **v11; // rsi
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  void *Pool2; // rax
  const char *v16; // rcx
  const char *v17; // [rsp+50h] [rbp+20h] BYREF
  int v18; // [rsp+58h] [rbp+28h] BYREF

  LOWORD(v18) = a2;
  *(_QWORD *)a4 = 0;
  v5 = -1073741811;
  if ( *(_DWORD *)(a1 + 28) != 1 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v17 = "Unexpected filter condition count";
      v9 = (__int64 *)&dword_14000EF6C;
LABEL_27:
      v18 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)v6,
        (unsigned __int8 *)v9,
        v7,
        v8,
        (int **)&v17,
        (__int64)&v18);
      return v5;
    }
    return v5;
  }
  v10 = *(_QWORD *)(a1 + 32);
  if ( *(_WORD *)v10 )
  {
    if ( *(_WORD *)v10 != (_WORD)a3 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      if ( (unsigned int)dword_140012050 <= 2 )
        return v5;
      v16 = "Unexpected filter condition";
      v9 = (__int64 *)byte_14000E8CD;
      goto LABEL_26;
    }
    if ( *(_DWORD *)(v10 + 8) != 13 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v17 = "Unexpected PackageId value type";
        v9 = qword_14000EBF8;
        goto LABEL_27;
      }
      return v5;
    }
    v5 = RoutePolicyCache::AppIdFromPackageId(*(unsigned __int8 **)(v10 + 16), a4, a3);
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v17 = "RoutePolicyCache::AppIdFromPackageId failed";
        v9 = qword_14000FC10;
        goto LABEL_27;
      }
      return v5;
    }
    return 0;
  }
  if ( *(_DWORD *)(v10 + 8) != 12 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v17 = "Unexpected AppId value type";
      v9 = (__int64 *)word_14000EEEA;
      goto LABEL_27;
    }
    return v5;
  }
  v11 = *(const void ***)(v10 + 16);
  v12 = *(unsigned int *)v11;
  v13 = v12 + 2;
  if ( v12 + 2 >= v12 )
  {
    Pool2 = (void *)ExAllocatePool2(64, v12 + 2, 1684435058);
    *(_QWORD *)a4 = Pool2;
    if ( !Pool2 )
    {
      v5 = -1073741670;
      if ( (unsigned int)dword_140012050 <= 2 )
        return v5;
      v16 = "Failed to allocate AppId";
      v9 = (__int64 *)&byte_1400101DF;
LABEL_26:
      v17 = v16;
      v6 = &v17;
      goto LABEL_27;
    }
    memmove(Pool2, v11[1], *(unsigned int *)v11);
    *(_WORD *)(*(_QWORD *)a4 + 2 * (v13 >> 1) - 2) = 0;
    return 0;
  }
  if ( (unsigned int)dword_140012050 > 2 )
  {
    v18 = -1073741675;
    v17 = "Failed to calculate AppId size";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v10,
      (unsigned __int8 *)byte_14000F163,
      (__int64)a3,
      (__int64)a4,
      (int **)&v17,
      (__int64)&v18);
  }
  return 3221225621LL;
}

```

## disassembly

```asm
0x1400030dc  mov     [rsp-18h+arg_10], rbx
0x1400030e1  mov     [rsp-18h+arg_18], rsi
0x1400030e6  mov     word ptr [rsp-18h+arg_8], dx
0x1400030eb  push    rbp
0x1400030ec  push    rdi
0x1400030ed  push    r14
0x1400030ef  mov     rbp, rsp
0x1400030f2  sub     rsp, 30h
0x1400030f6  xor     r14d, r14d
0x1400030f9  mov     rdi, r9
0x1400030fc  mov     [r9], r14
0x1400030ff  mov     ebx, 0C000000Dh
0x140003104  cmp     dword ptr [rcx+1Ch], 1
0x140003108  jz      short loc_140003147
0x14000310a  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000310f  mov     eax, cs:dword_140012050
0x140003115  cmp     eax, 2
0x140003118  jbe     loc_140003322
0x14000311e  lea     rax, aUnexpectedFilt; "Unexpected filter condition count"
0x140003125  mov     [rbp+arg_0], rax
0x140003129  lea     rdx, dword_14000EF6C
0x140003130  lea     rax, [rbp+arg_8]
0x140003134  mov     [rsp+30h+var_8], rax
0x140003139  lea     rax, [rbp+arg_0]
0x14000313d  mov     [rsp+30h+var_10], rax
0x140003142  jmp     loc_14000331A
0x140003147  mov     rcx, [rcx+20h]
0x14000314b  movzx   eax, word ptr [rcx]
0x14000314e  test    ax, ax
0x140003151  jnz     loc_140003259
0x140003157  cmp     dword ptr [rcx+8], 0Ch
0x14000315b  jz      short loc_14000319A
0x14000315d  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140003162  mov     eax, cs:dword_140012050
0x140003168  cmp     eax, 2
0x14000316b  jbe     loc_140003322
0x140003171  lea     rax, aUnexpectedAppi; "Unexpected AppId value type"
0x140003178  mov     [rbp+arg_0], rax
0x14000317c  lea     rdx, word_14000EEEA
0x140003183  lea     rax, [rbp+arg_8]
0x140003187  mov     [rsp+30h+var_8], rax
0x14000318c  lea     rax, [rbp+arg_0]
0x140003190  mov     [rsp+30h+var_10], rax
0x140003195  jmp     loc_14000331A
0x14000319a  mov     rsi, [rcx+10h]
0x14000319e  mov     eax, [rsi]
0x1400031a0  lea     rbx, [rax+2]
0x1400031a4  cmp     rbx, rax
0x1400031a7  jnb     short loc_1400031EE
0x1400031a9  mov     eax, cs:dword_140012050
0x1400031af  cmp     eax, 2
0x1400031b2  jbe     short loc_1400031E4
0x1400031b4  lea     rax, aFailedToCalcul; "Failed to calculate AppId size"
0x1400031bb  mov     [rbp+arg_8], 0C0000095h
0x1400031c2  mov     [rbp+arg_0], rax
0x1400031c6  lea     rdx, byte_14000F163
0x1400031cd  lea     rax, [rbp+arg_8]
0x1400031d1  mov     [rsp+30h+var_8], rax
0x1400031d6  lea     rax, [rbp+arg_0]
0x1400031da  mov     [rsp+30h+var_10], rax
0x1400031df  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400031e4  mov     eax, 0C0000095h
0x1400031e9  jmp     loc_140003324
0x1400031ee  mov     r8d, 64667072h
0x1400031f4  mov     rdx, rbx
0x1400031f7  mov     ecx, 40h ; '@'
0x1400031fc  call    cs:__imp_ExAllocatePool2
0x140003203  nop     dword ptr [rax+rax+00h]
0x140003208  mov     [rdi], rax
0x14000320b  test    rax, rax
0x14000320e  jnz     short loc_140003237
0x140003210  mov     eax, cs:dword_140012050
0x140003216  mov     ebx, 0C000009Ah
0x14000321b  cmp     eax, 2
0x14000321e  jbe     loc_140003322
0x140003224  lea     rcx, aFailedToAlloca_3; "Failed to allocate AppId"
0x14000322b  lea     rdx, byte_1400101DF
0x140003232  jmp     loc_140003304
0x140003237  mov     r8d, [rsi]; Size
0x14000323a  mov     rcx, rax; void *
0x14000323d  mov     rdx, [rsi+8]; Src
0x140003241  call    memmove
0x140003246  mov     rcx, [rdi]
0x140003249  shr     rbx, 1
0x14000324c  mov     [rcx+rbx*2-2], r14w
0x140003252  xor     eax, eax
0x140003254  jmp     loc_140003324
0x140003259  cmp     ax, r8w
0x14000325d  jnz     loc_1400032E6
0x140003263  cmp     dword ptr [rcx+8], 0Dh
0x140003267  jz      short loc_1400032A3
0x140003269  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000326e  mov     eax, cs:dword_140012050
0x140003274  cmp     eax, 2
0x140003277  jbe     loc_140003322
0x14000327d  lea     rax, aUnexpectedPack; "Unexpected PackageId value type"
0x140003284  mov     [rbp+arg_0], rax
0x140003288  lea     rdx, qword_14000EBF8
0x14000328f  lea     rax, [rbp+arg_8]
0x140003293  mov     [rsp+30h+var_8], rax
0x140003298  lea     rax, [rbp+arg_0]
0x14000329c  mov     [rsp+30h+var_10], rax
0x1400032a1  jmp     short loc_14000331A
0x1400032a3  mov     rcx, [rcx+10h]; Sid2
0x1400032a7  mov     rdx, rdi; this
0x1400032aa  call    ?AppIdFromPackageId@RoutePolicyCache@@YAJPEAXPEAPEAG@Z; RoutePolicyCache::AppIdFromPackageId(void *,ushort * *)
0x1400032af  mov     ebx, eax
0x1400032b1  test    eax, eax
0x1400032b3  jns     short loc_140003252
0x1400032b5  mov     eax, cs:dword_140012050
0x1400032bb  cmp     eax, 2
0x1400032be  jbe     short loc_140003322
0x1400032c0  lea     rax, aRoutepolicycac; "RoutePolicyCache::AppIdFromPackageId fa"...
0x1400032c7  mov     [rbp+arg_0], rax
0x1400032cb  lea     rdx, qword_14000FC10
0x1400032d2  lea     rax, [rbp+arg_8]
0x1400032d6  mov     [rsp+30h+var_8], rax
0x1400032db  lea     rax, [rbp+arg_0]
0x1400032df  mov     [rsp+30h+var_10], rax
0x1400032e4  jmp     short loc_14000331A
0x1400032e6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400032eb  mov     eax, cs:dword_140012050
0x1400032f1  cmp     eax, 2
0x1400032f4  jbe     short loc_140003322
0x1400032f6  lea     rcx, aUnexpectedFilt_0; "Unexpected filter condition"
0x1400032fd  lea     rdx, byte_14000E8CD
0x140003304  mov     [rbp+arg_0], rcx
0x140003308  lea     rcx, [rbp+arg_8]
0x14000330c  mov     [rsp+30h+var_8], rcx
0x140003311  lea     rcx, [rbp+arg_0]
0x140003315  mov     [rsp+30h+var_10], rcx
0x14000331a  mov     [rbp+arg_8], ebx
0x14000331d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003322  mov     eax, ebx
0x140003324  mov     rbx, [rsp+30h+arg_10]
0x140003329  mov     rsi, [rsp+30h+arg_18]
0x14000332e  add     rsp, 30h
0x140003332  pop     r14
0x140003334  pop     rdi
0x140003335  pop     rbp
0x140003336  retn
```

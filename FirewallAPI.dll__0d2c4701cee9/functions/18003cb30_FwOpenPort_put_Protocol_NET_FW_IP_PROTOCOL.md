# FwOpenPort::put_Protocol(NET_FW_IP_PROTOCOL_)

- ea: `0x18003cb30`
- end: `0x18003ccf0`
- name: `?put_Protocol@FwOpenPort@@UEAAJW4NET_FW_IP_PROTOCOL_@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_IP_PROTOCOL_)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18003bd9c`
- `0x18003cb30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cb70`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cb70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cca3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cca3`
- `fwbase!FwReportReturnError` at `0x18003cc93`
- `fwbase!FwReportReturnError` at `0x18003ccb8`
- `fwbase!FwReportReturnError` at `0x18003cc93`
- `fwbase!FwReportReturnError` at `0x18003ccb8`
- `FWPolicyIOMgr!FwICFProtocolToWfProtocol` at `0x18003cc6c`
- `FWPolicyIOMgr!FwICFProtocolToWfProtocol` at `0x18003cc6c`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003cba9`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003cba9`

## string_xrefs

- `0x18003cb7c`: `FwOpenPort::put_Protocol`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_Protocol(FwOpenPort *this, unsigned int a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  struct _tag_FW_RULE **v6; // rsi
  int DefaultOpenPortRule; // eax
  struct _tag_FW_RULE *v8; // rax
  _OWORD *v9; // rdx
  __int64 v10; // rcx
  __int128 v11; // xmm1
  _BYTE v13[48]; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v14[464]; // [rsp+50h] [rbp-208h] BYREF

  memset_0(v13, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 != 6 && a2 != 17 )
  {
    v4 = -2147024809;
LABEL_4:
    v5 = v4;
LABEL_13:
    FwReportReturnError("FwOpenPort::put_Protocol", v5);
    goto LABEL_14;
  }
  v6 = (struct _tag_FW_RULE **)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v4 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
      goto LABEL_12;
  }
  if ( *((_DWORD *)this + 20) )
  {
    v4 = -2147024891;
    goto LABEL_4;
  }
  v8 = *v6;
  v9 = v13;
  v10 = 3;
  do
  {
    *v9 = *(_OWORD *)v8;
    v9[1] = *((_OWORD *)v8 + 1);
    v9[2] = *((_OWORD *)v8 + 2);
    v9[3] = *((_OWORD *)v8 + 3);
    v9[4] = *((_OWORD *)v8 + 4);
    v9[5] = *((_OWORD *)v8 + 5);
    v9[6] = *((_OWORD *)v8 + 6);
    v11 = *((_OWORD *)v8 + 7);
    v8 = (struct _tag_FW_RULE *)((char *)v8 + 128);
    v9[7] = v11;
    v9 += 8;
    --v10;
  }
  while ( v10 );
  *v9 = *(_OWORD *)v8;
  v9[1] = *((_OWORD *)v8 + 1);
  v9[2] = *((_OWORD *)v8 + 2);
  v9[3] = *((_OWORD *)v8 + 3);
  v9[4] = *((_OWORD *)v8 + 4);
  v9[5] = *((_OWORD *)v8 + 5);
  v9[6] = *((_OWORD *)v8 + 6);
  *((_QWORD *)v9 + 14) = *((_QWORD *)v8 + 14);
  FwICFProtocolToWfProtocol(a2, v14, 128);
  DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v13, *v6);
  v4 = DefaultOpenPortRule;
  if ( DefaultOpenPortRule < 0 )
  {
LABEL_12:
    v5 = (unsigned int)DefaultOpenPortRule;
    goto LABEL_13;
  }
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (v4 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_Protocol", v4);
  return v4;
}

```

## disassembly

```asm
0x18003cb30  mov     [rsp+arg_10], rbx
0x18003cb35  push    rbp
0x18003cb36  push    rsi
0x18003cb37  push    rdi
0x18003cb38  push    r14
0x18003cb3a  push    r15
0x18003cb3c  sub     rsp, 230h
0x18003cb43  mov     rax, cs:__security_cookie
0x18003cb4a  xor     rax, rsp
0x18003cb4d  mov     [rsp+258h+var_38], rax
0x18003cb55  mov     ebp, edx
0x18003cb57  mov     rdi, rcx
0x18003cb5a  xor     edx, edx; Val
0x18003cb5c  lea     rcx, [rsp+258h+var_238]; void *
0x18003cb61  mov     r8d, 1F8h; Size
0x18003cb67  call    memset_0
0x18003cb6c  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003cb70  call    cs:__imp_EnterCriticalSection
0x18003cb77  nop     dword ptr [rax+rax+00h]
0x18003cb7c  lea     r15, aFwopenportPutP_0; "FwOpenPort::put_Protocol"
0x18003cb83  cmp     ebp, 6
0x18003cb86  jz      short loc_18003CB99
0x18003cb88  cmp     ebp, 11h
0x18003cb8b  jz      short loc_18003CB99
0x18003cb8d  mov     ebx, 80070057h
0x18003cb92  mov     edx, ebx
0x18003cb94  jmp     loc_18003CC90
0x18003cb99  lea     rsi, [rdi+48h]
0x18003cb9d  cmp     qword ptr [rsi], 0
0x18003cba1  jnz     short loc_18003CBBF
0x18003cba3  mov     edx, [rdi+40h]
0x18003cba6  mov     rcx, rsi
0x18003cba9  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003cbb0  nop     dword ptr [rax+rax+00h]
0x18003cbb5  mov     ebx, eax
0x18003cbb7  test    eax, eax
0x18003cbb9  js      loc_18003CC8E
0x18003cbbf  cmp     dword ptr [rdi+50h], 0
0x18003cbc3  jz      short loc_18003CBCC
0x18003cbc5  mov     ebx, 80070005h
0x18003cbca  jmp     short loc_18003CB92
0x18003cbcc  mov     rax, [rsi]
0x18003cbcf  lea     rdx, [rsp+258h+var_238]
0x18003cbd4  mov     ecx, 3
0x18003cbd9  lea     r8d, [rcx+7Dh]
0x18003cbdd  movups  xmm0, xmmword ptr [rax]
0x18003cbe0  movups  xmmword ptr [rdx], xmm0
0x18003cbe3  movups  xmm1, xmmword ptr [rax+10h]
0x18003cbe7  movups  xmmword ptr [rdx+10h], xmm1
0x18003cbeb  movups  xmm0, xmmword ptr [rax+20h]
0x18003cbef  movups  xmmword ptr [rdx+20h], xmm0
0x18003cbf3  movups  xmm1, xmmword ptr [rax+30h]
0x18003cbf7  movups  xmmword ptr [rdx+30h], xmm1
0x18003cbfb  movups  xmm0, xmmword ptr [rax+40h]
0x18003cbff  movups  xmmword ptr [rdx+40h], xmm0
0x18003cc03  movups  xmm1, xmmword ptr [rax+50h]
0x18003cc07  movups  xmmword ptr [rdx+50h], xmm1
0x18003cc0b  movups  xmm0, xmmword ptr [rax+60h]
0x18003cc0f  movups  xmmword ptr [rdx+60h], xmm0
0x18003cc13  movups  xmm1, xmmword ptr [rax+70h]
0x18003cc17  add     rax, r8
0x18003cc1a  movups  xmmword ptr [rdx+70h], xmm1
0x18003cc1e  add     rdx, r8
0x18003cc21  sub     rcx, 1
0x18003cc25  jnz     short loc_18003CBDD
0x18003cc27  movups  xmm0, xmmword ptr [rax]
0x18003cc2a  mov     ecx, ebp
0x18003cc2c  movups  xmmword ptr [rdx], xmm0
0x18003cc2f  movups  xmm1, xmmword ptr [rax+10h]
0x18003cc33  movups  xmmword ptr [rdx+10h], xmm1
0x18003cc37  movups  xmm0, xmmword ptr [rax+20h]
0x18003cc3b  movups  xmmword ptr [rdx+20h], xmm0
0x18003cc3f  movups  xmm1, xmmword ptr [rax+30h]
0x18003cc43  movups  xmmword ptr [rdx+30h], xmm1
0x18003cc47  movups  xmm0, xmmword ptr [rax+40h]
0x18003cc4b  movups  xmmword ptr [rdx+40h], xmm0
0x18003cc4f  movups  xmm1, xmmword ptr [rax+50h]
0x18003cc53  movups  xmmword ptr [rdx+50h], xmm1
0x18003cc57  movups  xmm0, xmmword ptr [rax+60h]
0x18003cc5b  movups  xmmword ptr [rdx+60h], xmm0
0x18003cc5f  mov     rax, [rax+70h]
0x18003cc63  mov     [rdx+70h], rax
0x18003cc67  lea     rdx, [rsp+258h+var_208]
0x18003cc6c  call    cs:__imp_FwICFProtocolToWfProtocol
0x18003cc73  nop     dword ptr [rax+rax+00h]
0x18003cc78  mov     r8, [rsi]; struct _tag_FW_RULE *
0x18003cc7b  lea     rdx, [rsp+258h+var_238]; struct _tag_FW_RULE *
0x18003cc80  mov     rcx, rdi; this
0x18003cc83  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003cc88  mov     ebx, eax
0x18003cc8a  test    eax, eax
0x18003cc8c  jns     short loc_18003CC9F
0x18003cc8e  mov     edx, eax
0x18003cc90  mov     rcx, r15
0x18003cc93  call    cs:__imp_FwReportReturnError
0x18003cc9a  nop     dword ptr [rax+rax+00h]
0x18003cc9f  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003cca3  call    cs:__imp_LeaveCriticalSection
0x18003ccaa  nop     dword ptr [rax+rax+00h]
0x18003ccaf  test    ebx, ebx
0x18003ccb1  jns     short loc_18003CCC6
0x18003ccb3  mov     edx, ebx
0x18003ccb5  mov     rcx, r15
0x18003ccb8  call    cs:__imp_FwReportReturnError
0x18003ccbf  nop     dword ptr [rax+rax+00h]
0x18003ccc4  mov     ebx, eax
0x18003ccc6  mov     eax, ebx
0x18003ccc8  mov     rcx, [rsp+258h+var_38]
0x18003ccd0  xor     rcx, rsp; StackCookie
0x18003ccd3  call    __security_check_cookie
0x18003ccd8  mov     rbx, [rsp+258h+arg_10]
0x18003cce0  add     rsp, 230h
0x18003cce7  pop     r15
0x18003cce9  pop     r14
0x18003cceb  pop     rdi
0x18003ccec  pop     rsi
0x18003cced  pop     rbp
0x18003ccee  retn
```

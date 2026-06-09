# FwOpenPort::put_Protocol(NET_FW_IP_PROTOCOL_)

- ea: `0x180039eb0`
- end: `0x18003a04b`
- name: `?put_Protocol@FwOpenPort@@UEAAJW4NET_FW_IP_PROTOCOL_@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_IP_PROTOCOL_)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x1800392c0`
- `0x180039eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039ef0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039ef0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a00b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a00b`
- `fwbase!FwReportReturnError` at `0x18003a001`
- `fwbase!FwReportReturnError` at `0x18003a01a`
- `fwbase!FwReportReturnError` at `0x18003a001`
- `fwbase!FwReportReturnError` at `0x18003a01a`
- `FWPolicyIOMgr!FwICFProtocolToWfProtocol` at `0x180039fe0`
- `FWPolicyIOMgr!FwICFProtocolToWfProtocol` at `0x180039fe0`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039f23`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039f23`

## string_xrefs

- `0x180039ef6`: `FwOpenPort::put_Protocol`

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
0x180039eb0  mov     [rsp+arg_10], rbx
0x180039eb5  push    rbp
0x180039eb6  push    rsi
0x180039eb7  push    rdi
0x180039eb8  push    r14
0x180039eba  push    r15
0x180039ebc  sub     rsp, 230h
0x180039ec3  mov     rax, cs:__security_cookie
0x180039eca  xor     rax, rsp
0x180039ecd  mov     [rsp+258h+var_38], rax
0x180039ed5  mov     ebp, edx
0x180039ed7  mov     rdi, rcx
0x180039eda  xor     edx, edx; Val
0x180039edc  lea     rcx, [rsp+258h+var_238]; void *
0x180039ee1  mov     r8d, 1F8h; Size
0x180039ee7  call    memset_0
0x180039eec  lea     rcx, [rdi+10h]; lpCriticalSection
0x180039ef0  call    cs:__imp_EnterCriticalSection
0x180039ef6  lea     r15, aFwopenportPutP_0; "FwOpenPort::put_Protocol"
0x180039efd  cmp     ebp, 6
0x180039f00  jz      short loc_180039F13
0x180039f02  cmp     ebp, 11h
0x180039f05  jz      short loc_180039F13
0x180039f07  mov     ebx, 80070057h
0x180039f0c  mov     edx, ebx
0x180039f0e  jmp     loc_180039FFE
0x180039f13  lea     rsi, [rdi+48h]
0x180039f17  cmp     qword ptr [rsi], 0
0x180039f1b  jnz     short loc_180039F33
0x180039f1d  mov     edx, [rdi+40h]
0x180039f20  mov     rcx, rsi
0x180039f23  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180039f29  mov     ebx, eax
0x180039f2b  test    eax, eax
0x180039f2d  js      loc_180039FFC
0x180039f33  cmp     dword ptr [rdi+50h], 0
0x180039f37  jz      short loc_180039F40
0x180039f39  mov     ebx, 80070005h
0x180039f3e  jmp     short loc_180039F0C
0x180039f40  mov     rax, [rsi]
0x180039f43  lea     rdx, [rsp+258h+var_238]
0x180039f48  mov     ecx, 3
0x180039f4d  lea     r8d, [rcx+7Dh]
0x180039f51  movups  xmm0, xmmword ptr [rax]
0x180039f54  movups  xmmword ptr [rdx], xmm0
0x180039f57  movups  xmm1, xmmword ptr [rax+10h]
0x180039f5b  movups  xmmword ptr [rdx+10h], xmm1
0x180039f5f  movups  xmm0, xmmword ptr [rax+20h]
0x180039f63  movups  xmmword ptr [rdx+20h], xmm0
0x180039f67  movups  xmm1, xmmword ptr [rax+30h]
0x180039f6b  movups  xmmword ptr [rdx+30h], xmm1
0x180039f6f  movups  xmm0, xmmword ptr [rax+40h]
0x180039f73  movups  xmmword ptr [rdx+40h], xmm0
0x180039f77  movups  xmm1, xmmword ptr [rax+50h]
0x180039f7b  movups  xmmword ptr [rdx+50h], xmm1
0x180039f7f  movups  xmm0, xmmword ptr [rax+60h]
0x180039f83  movups  xmmword ptr [rdx+60h], xmm0
0x180039f87  movups  xmm1, xmmword ptr [rax+70h]
0x180039f8b  add     rax, r8
0x180039f8e  movups  xmmword ptr [rdx+70h], xmm1
0x180039f92  add     rdx, r8
0x180039f95  sub     rcx, 1
0x180039f99  jnz     short loc_180039F51
0x180039f9b  movups  xmm0, xmmword ptr [rax]
0x180039f9e  mov     ecx, ebp
0x180039fa0  movups  xmmword ptr [rdx], xmm0
0x180039fa3  movups  xmm1, xmmword ptr [rax+10h]
0x180039fa7  movups  xmmword ptr [rdx+10h], xmm1
0x180039fab  movups  xmm0, xmmword ptr [rax+20h]
0x180039faf  movups  xmmword ptr [rdx+20h], xmm0
0x180039fb3  movups  xmm1, xmmword ptr [rax+30h]
0x180039fb7  movups  xmmword ptr [rdx+30h], xmm1
0x180039fbb  movups  xmm0, xmmword ptr [rax+40h]
0x180039fbf  movups  xmmword ptr [rdx+40h], xmm0
0x180039fc3  movups  xmm1, xmmword ptr [rax+50h]
0x180039fc7  movups  xmmword ptr [rdx+50h], xmm1
0x180039fcb  movups  xmm0, xmmword ptr [rax+60h]
0x180039fcf  movups  xmmword ptr [rdx+60h], xmm0
0x180039fd3  mov     rax, [rax+70h]
0x180039fd7  mov     [rdx+70h], rax
0x180039fdb  lea     rdx, [rsp+258h+var_208]
0x180039fe0  call    cs:__imp_FwICFProtocolToWfProtocol
0x180039fe6  mov     r8, [rsi]; struct _tag_FW_RULE *
0x180039fe9  lea     rdx, [rsp+258h+var_238]; struct _tag_FW_RULE *
0x180039fee  mov     rcx, rdi; this
0x180039ff1  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x180039ff6  mov     ebx, eax
0x180039ff8  test    eax, eax
0x180039ffa  jns     short loc_18003A007
0x180039ffc  mov     edx, eax
0x180039ffe  mov     rcx, r15
0x18003a001  call    cs:__imp_FwReportReturnError
0x18003a007  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003a00b  call    cs:__imp_LeaveCriticalSection
0x18003a011  test    ebx, ebx
0x18003a013  jns     short loc_18003A022
0x18003a015  mov     edx, ebx
0x18003a017  mov     rcx, r15
0x18003a01a  call    cs:__imp_FwReportReturnError
0x18003a020  mov     ebx, eax
0x18003a022  mov     eax, ebx
0x18003a024  mov     rcx, [rsp+258h+var_38]
0x18003a02c  xor     rcx, rsp; StackCookie
0x18003a02f  call    __security_check_cookie
0x18003a034  mov     rbx, [rsp+258h+arg_10]
0x18003a03c  add     rsp, 230h
0x18003a043  pop     r15
0x18003a045  pop     r14
0x18003a047  pop     rdi
0x18003a048  pop     rsi
0x18003a049  pop     rbp
0x18003a04a  retn
```

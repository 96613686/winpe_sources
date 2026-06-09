# FwOpenPort::put_RemoteAddresses(ushort *)

- ea: `0x18003cd00`
- end: `0x18003cf03`
- name: `?put_RemoteAddresses@FwOpenPort@@UEAAJPEAG@Z`
- size: `515`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18003bd9c`
- `0x18003cd00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cd5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003cd5a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cea1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cea1`
- `fwbase!FwReportReturnError` at `0x18003ce91`
- `fwbase!FwReportReturnError` at `0x18003cecb`
- `fwbase!FwReportReturnError` at `0x18003ce91`
- `fwbase!FwReportReturnError` at `0x18003cecb`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003cd6e`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003cd6e`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003cd94`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003cd94`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003ceb2`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003ceb2`

## string_xrefs

- `0x18003ce8a`: `FwOpenPort::put_RemoteAddresses`
- `0x18003cec4`: `FwOpenPort::put_RemoteAddresses`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_RemoteAddresses(FwOpenPort *this, unsigned __int16 *a2)
{
  int DefaultOpenPortRule; // eax
  int v5; // ebx
  struct _tag_FW_RULE **v6; // rdi
  struct _tag_FW_RULE *v7; // rax
  _OWORD *v8; // rdx
  __int64 v9; // rcx
  __int128 v10; // xmm1
  struct _tag_FW_RULE *v11; // r8
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  _OWORD v15[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  _BYTE v17[176]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v18; // [rsp+120h] [rbp+20h]
  __int128 v19; // [rsp+130h] [rbp+30h]
  __int128 v20; // [rsp+140h] [rbp+40h]
  __int128 v21; // [rsp+150h] [rbp+50h]
  __int64 v22; // [rsp+160h] [rbp+60h]

  memset_0(v15, 0, 0x48u);
  memset_0(v17, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DefaultOpenPortRule = StringToOpenPortOrAuthAppAddress(a2, v15);
  v5 = DefaultOpenPortRule;
  if ( DefaultOpenPortRule < 0 )
    goto LABEL_7;
  v6 = (struct _tag_FW_RULE **)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v5 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
      goto LABEL_7;
  }
  v7 = *v6;
  v8 = v17;
  v9 = 3;
  do
  {
    *v8 = *(_OWORD *)v7;
    v8[1] = *((_OWORD *)v7 + 1);
    v8[2] = *((_OWORD *)v7 + 2);
    v8[3] = *((_OWORD *)v7 + 3);
    v8[4] = *((_OWORD *)v7 + 4);
    v8[5] = *((_OWORD *)v7 + 5);
    v8[6] = *((_OWORD *)v7 + 6);
    v10 = *((_OWORD *)v7 + 7);
    v7 = (struct _tag_FW_RULE *)((char *)v7 + 128);
    v8[7] = v10;
    v8 += 8;
    --v9;
  }
  while ( v9 );
  v11 = *v6;
  *v8 = *(_OWORD *)v7;
  v8[1] = *((_OWORD *)v7 + 1);
  v8[2] = *((_OWORD *)v7 + 2);
  v8[3] = *((_OWORD *)v7 + 3);
  v8[4] = *((_OWORD *)v7 + 4);
  v8[5] = *((_OWORD *)v7 + 5);
  v12 = v15[1];
  v8[6] = *((_OWORD *)v7 + 6);
  v13 = v15[0];
  *((_QWORD *)v8 + 14) = *((_QWORD *)v7 + 14);
  v18 = v13;
  v20 = v15[2];
  v19 = v12;
  v22 = v16;
  v21 = v15[3];
  DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v17, v11);
  v5 = DefaultOpenPortRule;
  if ( DefaultOpenPortRule < 0 )
LABEL_7:
    FwReportReturnError("FwOpenPort::put_RemoteAddresses", (unsigned int)DefaultOpenPortRule);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  FwPolioEmptyWFAddresses(v15);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003cd00  mov     [rsp-8+arg_10], rbx
0x18003cd05  mov     [rsp-8+arg_18], rsi
0x18003cd0a  push    rbp
0x18003cd0b  push    rdi
0x18003cd0c  push    r14
0x18003cd0e  lea     rbp, [rsp-180h]
0x18003cd16  sub     rsp, 280h
0x18003cd1d  mov     rax, cs:__security_cookie
0x18003cd24  xor     rax, rsp
0x18003cd27  mov     [rbp+190h+var_20], rax
0x18003cd2e  mov     rbx, rdx
0x18003cd31  mov     rsi, rcx
0x18003cd34  xor     edx, edx; Val
0x18003cd36  lea     rcx, [rsp+290h+var_270]; void *
0x18003cd3b  lea     r8d, [rdx+48h]; Size
0x18003cd3f  call    memset_0
0x18003cd44  xor     edx, edx; Val
0x18003cd46  lea     rcx, [rsp+290h+var_220]; void *
0x18003cd4b  mov     r8d, 1F8h; Size
0x18003cd51  call    memset_0
0x18003cd56  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003cd5a  call    cs:__imp_EnterCriticalSection
0x18003cd61  nop     dword ptr [rax+rax+00h]
0x18003cd66  lea     rdx, [rsp+290h+var_270]
0x18003cd6b  mov     rcx, rbx
0x18003cd6e  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x18003cd75  nop     dword ptr [rax+rax+00h]
0x18003cd7a  mov     ebx, eax
0x18003cd7c  test    eax, eax
0x18003cd7e  js      loc_18003CE88
0x18003cd84  lea     rdi, [rsi+48h]
0x18003cd88  cmp     qword ptr [rdi], 0
0x18003cd8c  jnz     short loc_18003CDAA
0x18003cd8e  mov     edx, [rsi+40h]
0x18003cd91  mov     rcx, rdi
0x18003cd94  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003cd9b  nop     dword ptr [rax+rax+00h]
0x18003cda0  mov     ebx, eax
0x18003cda2  test    eax, eax
0x18003cda4  js      loc_18003CE88
0x18003cdaa  mov     rax, [rdi]
0x18003cdad  lea     rdx, [rsp+290h+var_220]
0x18003cdb2  mov     ecx, 3
0x18003cdb7  lea     r8d, [rcx+7Dh]
0x18003cdbb  movups  xmm0, xmmword ptr [rax]
0x18003cdbe  movups  xmmword ptr [rdx], xmm0
0x18003cdc1  movups  xmm1, xmmword ptr [rax+10h]
0x18003cdc5  movups  xmmword ptr [rdx+10h], xmm1
0x18003cdc9  movups  xmm0, xmmword ptr [rax+20h]
0x18003cdcd  movups  xmmword ptr [rdx+20h], xmm0
0x18003cdd1  movups  xmm1, xmmword ptr [rax+30h]
0x18003cdd5  movups  xmmword ptr [rdx+30h], xmm1
0x18003cdd9  movups  xmm0, xmmword ptr [rax+40h]
0x18003cddd  movups  xmmword ptr [rdx+40h], xmm0
0x18003cde1  movups  xmm1, xmmword ptr [rax+50h]
0x18003cde5  movups  xmmword ptr [rdx+50h], xmm1
0x18003cde9  movups  xmm0, xmmword ptr [rax+60h]
0x18003cded  movups  xmmword ptr [rdx+60h], xmm0
0x18003cdf1  movups  xmm1, xmmword ptr [rax+70h]
0x18003cdf5  add     rax, r8
0x18003cdf8  movups  xmmword ptr [rdx+70h], xmm1
0x18003cdfc  add     rdx, r8
0x18003cdff  sub     rcx, 1
0x18003ce03  jnz     short loc_18003CDBB
0x18003ce05  movups  xmm0, xmmword ptr [rax]
0x18003ce08  mov     r8, [rdi]; struct _tag_FW_RULE *
0x18003ce0b  mov     rcx, rsi; this
0x18003ce0e  movups  xmmword ptr [rdx], xmm0
0x18003ce11  movups  xmm1, xmmword ptr [rax+10h]
0x18003ce15  movups  xmmword ptr [rdx+10h], xmm1
0x18003ce19  movups  xmm0, xmmword ptr [rax+20h]
0x18003ce1d  movups  xmmword ptr [rdx+20h], xmm0
0x18003ce21  movups  xmm1, xmmword ptr [rax+30h]
0x18003ce25  movups  xmmword ptr [rdx+30h], xmm1
0x18003ce29  movups  xmm0, xmmword ptr [rax+40h]
0x18003ce2d  movups  xmmword ptr [rdx+40h], xmm0
0x18003ce31  movups  xmm1, xmmword ptr [rax+50h]
0x18003ce35  movups  xmmword ptr [rdx+50h], xmm1
0x18003ce39  movups  xmm0, xmmword ptr [rax+60h]
0x18003ce3d  movaps  xmm1, [rsp+290h+var_260]
0x18003ce42  movups  xmmword ptr [rdx+60h], xmm0
0x18003ce46  mov     rax, [rax+70h]
0x18003ce4a  movaps  xmm0, [rsp+290h+var_270]
0x18003ce4f  mov     [rdx+70h], rax
0x18003ce53  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x18003ce58  movaps  [rbp+190h+var_170], xmm0
0x18003ce5c  movaps  xmm0, [rsp+290h+var_250]
0x18003ce61  movaps  [rbp+190h+var_150], xmm0
0x18003ce65  movsd   xmm0, [rsp+290h+var_230]
0x18003ce6b  movaps  [rbp+190h+var_160], xmm1
0x18003ce6f  movaps  xmm1, [rsp+290h+var_240]
0x18003ce74  movsd   [rbp+190h+var_130], xmm0
0x18003ce79  movaps  [rbp+190h+var_140], xmm1
0x18003ce7d  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003ce82  mov     ebx, eax
0x18003ce84  test    eax, eax
0x18003ce86  jns     short loc_18003CE9D
0x18003ce88  mov     edx, eax
0x18003ce8a  lea     rcx, aFwopenportPutR; "FwOpenPort::put_RemoteAddresses"
0x18003ce91  call    cs:__imp_FwReportReturnError
0x18003ce98  nop     dword ptr [rax+rax+00h]
0x18003ce9d  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003cea1  call    cs:__imp_LeaveCriticalSection
0x18003cea8  nop     dword ptr [rax+rax+00h]
0x18003cead  lea     rcx, [rsp+290h+var_270]
0x18003ceb2  call    cs:__imp_FwPolioEmptyWFAddresses
0x18003ceb9  nop     dword ptr [rax+rax+00h]
0x18003cebe  test    ebx, ebx
0x18003cec0  jns     short loc_18003CED9
0x18003cec2  mov     edx, ebx
0x18003cec4  lea     rcx, aFwopenportPutR; "FwOpenPort::put_RemoteAddresses"
0x18003cecb  call    cs:__imp_FwReportReturnError
0x18003ced2  nop     dword ptr [rax+rax+00h]
0x18003ced7  mov     ebx, eax
0x18003ced9  mov     eax, ebx
0x18003cedb  mov     rcx, [rbp+190h+var_20]
0x18003cee2  xor     rcx, rsp; StackCookie
0x18003cee5  call    __security_check_cookie
0x18003ceea  lea     r11, [rsp+290h+var_10]
0x18003cef2  mov     rbx, [r11+30h]
0x18003cef6  mov     rsi, [r11+38h]
0x18003cefa  mov     rsp, r11
0x18003cefd  pop     r14
0x18003ceff  pop     rdi
0x18003cf00  pop     rbp
0x18003cf01  retn
```

# FwOpenPort::put_RemoteAddresses(ushort *)

- ea: `0x18003a060`
- end: `0x18003a238`
- name: `?put_RemoteAddresses@FwOpenPort@@UEAAJPEAG@Z`
- size: `472`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x1800392c0`
- `0x18003a060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a0ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a0ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a1e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a1e9`
- `fwbase!FwReportReturnError` at `0x18003a1df`
- `fwbase!FwReportReturnError` at `0x18003a207`
- `fwbase!FwReportReturnError` at `0x18003a1df`
- `fwbase!FwReportReturnError` at `0x18003a207`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003a0c8`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003a0c8`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003a0e8`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003a0e8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003a1f4`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003a1f4`

## string_xrefs

- `0x18003a1d8`: `FwOpenPort::put_RemoteAddresses`
- `0x18003a200`: `FwOpenPort::put_RemoteAddresses`

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
0x18003a060  mov     [rsp-8+arg_10], rbx
0x18003a065  mov     [rsp-8+arg_18], rsi
0x18003a06a  push    rbp
0x18003a06b  push    rdi
0x18003a06c  push    r14
0x18003a06e  lea     rbp, [rsp-180h]
0x18003a076  sub     rsp, 280h
0x18003a07d  mov     rax, cs:__security_cookie
0x18003a084  xor     rax, rsp
0x18003a087  mov     [rbp+190h+var_20], rax
0x18003a08e  mov     rbx, rdx
0x18003a091  mov     rsi, rcx
0x18003a094  xor     edx, edx; Val
0x18003a096  lea     rcx, [rsp+290h+var_270]; void *
0x18003a09b  lea     r8d, [rdx+48h]; Size
0x18003a09f  call    memset_0
0x18003a0a4  xor     edx, edx; Val
0x18003a0a6  lea     rcx, [rsp+290h+var_220]; void *
0x18003a0ab  mov     r8d, 1F8h; Size
0x18003a0b1  call    memset_0
0x18003a0b6  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003a0ba  call    cs:__imp_EnterCriticalSection
0x18003a0c0  lea     rdx, [rsp+290h+var_270]
0x18003a0c5  mov     rcx, rbx
0x18003a0c8  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x18003a0ce  mov     ebx, eax
0x18003a0d0  test    eax, eax
0x18003a0d2  js      loc_18003A1D6
0x18003a0d8  lea     rdi, [rsi+48h]
0x18003a0dc  cmp     qword ptr [rdi], 0
0x18003a0e0  jnz     short loc_18003A0F8
0x18003a0e2  mov     edx, [rsi+40h]
0x18003a0e5  mov     rcx, rdi
0x18003a0e8  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003a0ee  mov     ebx, eax
0x18003a0f0  test    eax, eax
0x18003a0f2  js      loc_18003A1D6
0x18003a0f8  mov     rax, [rdi]
0x18003a0fb  lea     rdx, [rsp+290h+var_220]
0x18003a100  mov     ecx, 3
0x18003a105  lea     r8d, [rcx+7Dh]
0x18003a109  movups  xmm0, xmmword ptr [rax]
0x18003a10c  movups  xmmword ptr [rdx], xmm0
0x18003a10f  movups  xmm1, xmmword ptr [rax+10h]
0x18003a113  movups  xmmword ptr [rdx+10h], xmm1
0x18003a117  movups  xmm0, xmmword ptr [rax+20h]
0x18003a11b  movups  xmmword ptr [rdx+20h], xmm0
0x18003a11f  movups  xmm1, xmmword ptr [rax+30h]
0x18003a123  movups  xmmword ptr [rdx+30h], xmm1
0x18003a127  movups  xmm0, xmmword ptr [rax+40h]
0x18003a12b  movups  xmmword ptr [rdx+40h], xmm0
0x18003a12f  movups  xmm1, xmmword ptr [rax+50h]
0x18003a133  movups  xmmword ptr [rdx+50h], xmm1
0x18003a137  movups  xmm0, xmmword ptr [rax+60h]
0x18003a13b  movups  xmmword ptr [rdx+60h], xmm0
0x18003a13f  movups  xmm1, xmmword ptr [rax+70h]
0x18003a143  add     rax, r8
0x18003a146  movups  xmmword ptr [rdx+70h], xmm1
0x18003a14a  add     rdx, r8
0x18003a14d  sub     rcx, 1
0x18003a151  jnz     short loc_18003A109
0x18003a153  movups  xmm0, xmmword ptr [rax]
0x18003a156  mov     r8, [rdi]; struct _tag_FW_RULE *
0x18003a159  mov     rcx, rsi; this
0x18003a15c  movups  xmmword ptr [rdx], xmm0
0x18003a15f  movups  xmm1, xmmword ptr [rax+10h]
0x18003a163  movups  xmmword ptr [rdx+10h], xmm1
0x18003a167  movups  xmm0, xmmword ptr [rax+20h]
0x18003a16b  movups  xmmword ptr [rdx+20h], xmm0
0x18003a16f  movups  xmm1, xmmword ptr [rax+30h]
0x18003a173  movups  xmmword ptr [rdx+30h], xmm1
0x18003a177  movups  xmm0, xmmword ptr [rax+40h]
0x18003a17b  movups  xmmword ptr [rdx+40h], xmm0
0x18003a17f  movups  xmm1, xmmword ptr [rax+50h]
0x18003a183  movups  xmmword ptr [rdx+50h], xmm1
0x18003a187  movups  xmm0, xmmword ptr [rax+60h]
0x18003a18b  movaps  xmm1, [rsp+290h+var_260]
0x18003a190  movups  xmmword ptr [rdx+60h], xmm0
0x18003a194  mov     rax, [rax+70h]
0x18003a198  movaps  xmm0, [rsp+290h+var_270]
0x18003a19d  mov     [rdx+70h], rax
0x18003a1a1  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x18003a1a6  movaps  [rbp+190h+var_170], xmm0
0x18003a1aa  movaps  xmm0, [rsp+290h+var_250]
0x18003a1af  movaps  [rbp+190h+var_150], xmm0
0x18003a1b3  movsd   xmm0, [rsp+290h+var_230]
0x18003a1b9  movaps  [rbp+190h+var_160], xmm1
0x18003a1bd  movaps  xmm1, [rsp+290h+var_240]
0x18003a1c2  movsd   [rbp+190h+var_130], xmm0
0x18003a1c7  movaps  [rbp+190h+var_140], xmm1
0x18003a1cb  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003a1d0  mov     ebx, eax
0x18003a1d2  test    eax, eax
0x18003a1d4  jns     short loc_18003A1E5
0x18003a1d6  mov     edx, eax
0x18003a1d8  lea     rcx, aFwopenportPutR; "FwOpenPort::put_RemoteAddresses"
0x18003a1df  call    cs:__imp_FwReportReturnError
0x18003a1e5  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003a1e9  call    cs:__imp_LeaveCriticalSection
0x18003a1ef  lea     rcx, [rsp+290h+var_270]
0x18003a1f4  call    cs:__imp_FwPolioEmptyWFAddresses
0x18003a1fa  test    ebx, ebx
0x18003a1fc  jns     short loc_18003A20F
0x18003a1fe  mov     edx, ebx
0x18003a200  lea     rcx, aFwopenportPutR; "FwOpenPort::put_RemoteAddresses"
0x18003a207  call    cs:__imp_FwReportReturnError
0x18003a20d  mov     ebx, eax
0x18003a20f  mov     eax, ebx
0x18003a211  mov     rcx, [rbp+190h+var_20]
0x18003a218  xor     rcx, rsp; StackCookie
0x18003a21b  call    __security_check_cookie
0x18003a220  lea     r11, [rsp+290h+var_10]
0x18003a228  mov     rbx, [r11+30h]
0x18003a22c  mov     rsi, [r11+38h]
0x18003a230  mov     rsp, r11
0x18003a233  pop     r14
0x18003a235  pop     rdi
0x18003a236  pop     rbp
0x18003a237  retn
```

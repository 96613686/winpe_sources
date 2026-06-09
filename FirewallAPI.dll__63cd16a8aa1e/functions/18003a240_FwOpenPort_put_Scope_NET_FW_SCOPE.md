# FwOpenPort::put_Scope(NET_FW_SCOPE_)

- ea: `0x18003a240`
- end: `0x18003a416`
- name: `?put_Scope@FwOpenPort@@UEAAJW4NET_FW_SCOPE_@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, enum NET_FW_SCOPE_)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x1800392c0`
- `0x18003a240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a299`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a3d2`
- `fwbase!FwReportReturnError` at `0x18003a3c8`
- `fwbase!FwReportReturnError` at `0x18003a3e5`
- `fwbase!FwReportReturnError` at `0x18003a3c8`
- `fwbase!FwReportReturnError` at `0x18003a3e5`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003a2d1`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003a2d1`

## string_xrefs

- `0x18003a3c1`: `FwOpenPort::put_Scope`
- `0x18003a3de`: `FwOpenPort::put_Scope`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_Scope(FwOpenPort *this, enum NET_FW_SCOPE_ a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  struct _tag_FW_RULE **v6; // rdi
  int DefaultOpenPortRule; // eax
  struct _tag_FW_RULE *v8; // rax
  _OWORD *v9; // rdx
  __int64 v10; // rcx
  __int128 v11; // xmm1
  struct _tag_FW_RULE *v12; // r8
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  _OWORD v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h]
  _BYTE v18[176]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v19; // [rsp+120h] [rbp+20h]
  __int128 v20; // [rsp+130h] [rbp+30h]
  __int128 v21; // [rsp+140h] [rbp+40h]
  __int128 v22; // [rsp+150h] [rbp+50h]
  __int64 v23; // [rsp+160h] [rbp+60h]

  memset_0(v16, 0, 0x48u);
  memset_0(v18, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    if ( a2 != NET_FW_SCOPE_LOCAL_SUBNET )
    {
      v4 = -2147024809;
      v5 = 2147942487LL;
      goto LABEL_11;
    }
    *(_QWORD *)&v16[0] = 0x100000001LL;
  }
  v6 = (struct _tag_FW_RULE **)((char *)this + 72);
  if ( *((_QWORD *)this + 9)
    || (DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16)),
        v4 = DefaultOpenPortRule,
        DefaultOpenPortRule >= 0) )
  {
    v8 = *v6;
    v9 = v18;
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
    v12 = *v6;
    *v9 = *(_OWORD *)v8;
    v9[1] = *((_OWORD *)v8 + 1);
    v9[2] = *((_OWORD *)v8 + 2);
    v9[3] = *((_OWORD *)v8 + 3);
    v9[4] = *((_OWORD *)v8 + 4);
    v9[5] = *((_OWORD *)v8 + 5);
    v13 = v16[1];
    v9[6] = *((_OWORD *)v8 + 6);
    v14 = v16[0];
    *((_QWORD *)v9 + 14) = *((_QWORD *)v8 + 14);
    v19 = v14;
    v21 = v16[2];
    v20 = v13;
    v23 = v17;
    v22 = v16[3];
    DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v18, v12);
    v4 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule >= 0 )
      goto LABEL_12;
  }
  v5 = (unsigned int)DefaultOpenPortRule;
LABEL_11:
  FwReportReturnError("FwOpenPort::put_Scope", v5);
LABEL_12:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_Scope", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003a240  mov     [rsp-8+arg_8], rbx
0x18003a245  mov     [rsp-8+arg_10], rsi
0x18003a24a  push    rbp
0x18003a24b  push    rdi
0x18003a24c  push    r14
0x18003a24e  lea     rbp, [rsp-180h]
0x18003a256  sub     rsp, 280h
0x18003a25d  mov     rax, cs:__security_cookie
0x18003a264  xor     rax, rsp
0x18003a267  mov     [rbp+190h+var_20], rax
0x18003a26e  mov     ebx, edx
0x18003a270  mov     rsi, rcx
0x18003a273  xor     edx, edx; Val
0x18003a275  lea     rcx, [rsp+290h+var_270]; void *
0x18003a27a  lea     r8d, [rdx+48h]; Size
0x18003a27e  call    memset_0
0x18003a283  xor     edx, edx; Val
0x18003a285  lea     rcx, [rsp+290h+var_220]; void *
0x18003a28a  mov     r8d, 1F8h; Size
0x18003a290  call    memset_0
0x18003a295  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003a299  call    cs:__imp_EnterCriticalSection
0x18003a29f  test    ebx, ebx
0x18003a2a1  jz      short loc_18003A2C1
0x18003a2a3  cmp     ebx, 1
0x18003a2a6  jz      short loc_18003A2B4
0x18003a2a8  mov     ebx, 80070057h
0x18003a2ad  mov     edx, ebx
0x18003a2af  jmp     loc_18003A3C1
0x18003a2b4  mov     eax, 1
0x18003a2b9  mov     dword ptr [rsp+290h+var_270+4], eax
0x18003a2bd  mov     dword ptr [rsp+290h+var_270], eax
0x18003a2c1  lea     rdi, [rsi+48h]
0x18003a2c5  cmp     qword ptr [rdi], 0
0x18003a2c9  jnz     short loc_18003A2E1
0x18003a2cb  mov     edx, [rsi+40h]
0x18003a2ce  mov     rcx, rdi
0x18003a2d1  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003a2d7  mov     ebx, eax
0x18003a2d9  test    eax, eax
0x18003a2db  js      loc_18003A3BF
0x18003a2e1  mov     rax, [rdi]
0x18003a2e4  lea     rdx, [rsp+290h+var_220]
0x18003a2e9  mov     ecx, 3
0x18003a2ee  lea     r8d, [rcx+7Dh]
0x18003a2f2  movups  xmm0, xmmword ptr [rax]
0x18003a2f5  movups  xmmword ptr [rdx], xmm0
0x18003a2f8  movups  xmm1, xmmword ptr [rax+10h]
0x18003a2fc  movups  xmmword ptr [rdx+10h], xmm1
0x18003a300  movups  xmm0, xmmword ptr [rax+20h]
0x18003a304  movups  xmmword ptr [rdx+20h], xmm0
0x18003a308  movups  xmm1, xmmword ptr [rax+30h]
0x18003a30c  movups  xmmword ptr [rdx+30h], xmm1
0x18003a310  movups  xmm0, xmmword ptr [rax+40h]
0x18003a314  movups  xmmword ptr [rdx+40h], xmm0
0x18003a318  movups  xmm1, xmmword ptr [rax+50h]
0x18003a31c  movups  xmmword ptr [rdx+50h], xmm1
0x18003a320  movups  xmm0, xmmword ptr [rax+60h]
0x18003a324  movups  xmmword ptr [rdx+60h], xmm0
0x18003a328  movups  xmm1, xmmword ptr [rax+70h]
0x18003a32c  add     rax, r8
0x18003a32f  movups  xmmword ptr [rdx+70h], xmm1
0x18003a333  add     rdx, r8
0x18003a336  sub     rcx, 1
0x18003a33a  jnz     short loc_18003A2F2
0x18003a33c  movups  xmm0, xmmword ptr [rax]
0x18003a33f  mov     r8, [rdi]; struct _tag_FW_RULE *
0x18003a342  mov     rcx, rsi; this
0x18003a345  movups  xmmword ptr [rdx], xmm0
0x18003a348  movups  xmm1, xmmword ptr [rax+10h]
0x18003a34c  movups  xmmword ptr [rdx+10h], xmm1
0x18003a350  movups  xmm0, xmmword ptr [rax+20h]
0x18003a354  movups  xmmword ptr [rdx+20h], xmm0
0x18003a358  movups  xmm1, xmmword ptr [rax+30h]
0x18003a35c  movups  xmmword ptr [rdx+30h], xmm1
0x18003a360  movups  xmm0, xmmword ptr [rax+40h]
0x18003a364  movups  xmmword ptr [rdx+40h], xmm0
0x18003a368  movups  xmm1, xmmword ptr [rax+50h]
0x18003a36c  movups  xmmword ptr [rdx+50h], xmm1
0x18003a370  movups  xmm0, xmmword ptr [rax+60h]
0x18003a374  movaps  xmm1, [rsp+290h+var_260]
0x18003a379  movups  xmmword ptr [rdx+60h], xmm0
0x18003a37d  mov     rax, [rax+70h]
0x18003a381  movaps  xmm0, [rsp+290h+var_270]
0x18003a386  mov     [rdx+70h], rax
0x18003a38a  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x18003a38f  movaps  [rbp+190h+var_170], xmm0
0x18003a393  movaps  xmm0, [rsp+290h+var_250]
0x18003a398  movaps  [rbp+190h+var_150], xmm0
0x18003a39c  movsd   xmm0, [rsp+290h+var_230]
0x18003a3a2  movaps  [rbp+190h+var_160], xmm1
0x18003a3a6  movaps  xmm1, [rsp+290h+var_240]
0x18003a3ab  movsd   [rbp+190h+var_130], xmm0
0x18003a3b0  movaps  [rbp+190h+var_140], xmm1
0x18003a3b4  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003a3b9  mov     ebx, eax
0x18003a3bb  test    eax, eax
0x18003a3bd  jns     short loc_18003A3CE
0x18003a3bf  mov     edx, eax
0x18003a3c1  lea     rcx, aFwopenportPutS; "FwOpenPort::put_Scope"
0x18003a3c8  call    cs:__imp_FwReportReturnError
0x18003a3ce  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003a3d2  call    cs:__imp_LeaveCriticalSection
0x18003a3d8  test    ebx, ebx
0x18003a3da  jns     short loc_18003A3ED
0x18003a3dc  mov     edx, ebx
0x18003a3de  lea     rcx, aFwopenportPutS; "FwOpenPort::put_Scope"
0x18003a3e5  call    cs:__imp_FwReportReturnError
0x18003a3eb  mov     ebx, eax
0x18003a3ed  mov     eax, ebx
0x18003a3ef  mov     rcx, [rbp+190h+var_20]
0x18003a3f6  xor     rcx, rsp; StackCookie
0x18003a3f9  call    __security_check_cookie
0x18003a3fe  lea     r11, [rsp+290h+var_10]
0x18003a406  mov     rbx, [r11+28h]
0x18003a40a  mov     rsi, [r11+30h]
0x18003a40e  mov     rsp, r11
0x18003a411  pop     r14
0x18003a413  pop     rdi
0x18003a414  pop     rbp
0x18003a415  retn
```

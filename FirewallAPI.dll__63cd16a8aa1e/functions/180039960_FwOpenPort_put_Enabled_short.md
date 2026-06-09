# FwOpenPort::put_Enabled(short)

- ea: `0x180039960`
- end: `0x180039afc`
- name: `?put_Enabled@FwOpenPort@@UEAAJF@Z`
- size: `412`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x1800392c0`
- `0x180039960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800399a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800399a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ab7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ab7`
- `fwbase!FwReportReturnError` at `0x180039aad`
- `fwbase!FwReportReturnError` at `0x180039aca`
- `fwbase!FwReportReturnError` at `0x180039aad`
- `fwbase!FwReportReturnError` at `0x180039aca`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x1800399ba`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x1800399ba`

## string_xrefs

- `0x180039aa6`: `FwOpenPort::put_Enabled`
- `0x180039ac3`: `FwOpenPort::put_Enabled`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_Enabled(FwOpenPort *this, __int16 a2)
{
  struct _tag_FW_RULE **v4; // rsi
  int DefaultOpenPortRule; // eax
  int v6; // ebx
  struct _tag_FW_RULE *v7; // rax
  _OWORD *v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm1
  _BYTE v12[288]; // [rsp+20h] [rbp-228h] BYREF
  int v13; // [rsp+140h] [rbp-108h]
  __int16 v14; // [rsp+144h] [rbp-104h]

  memset_0(v12, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = (struct _tag_FW_RULE **)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v6 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
      goto LABEL_9;
  }
  v7 = *v4;
  v8 = v12;
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
  *v8 = *(_OWORD *)v7;
  v8[1] = *((_OWORD *)v7 + 1);
  v8[2] = *((_OWORD *)v7 + 2);
  v8[3] = *((_OWORD *)v7 + 3);
  v8[4] = *((_OWORD *)v7 + 4);
  v8[5] = *((_OWORD *)v7 + 5);
  v8[6] = *((_OWORD *)v7 + 6);
  *((_QWORD *)v8 + 14) = *((_QWORD *)v7 + 14);
  if ( a2 == -1 )
  {
    v14 |= 1u;
    v13 = 3;
  }
  else
  {
    v14 &= ~1u;
  }
  DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v12, *v4);
  v6 = DefaultOpenPortRule;
  if ( DefaultOpenPortRule < 0 )
LABEL_9:
    FwReportReturnError("FwOpenPort::put_Enabled", (unsigned int)DefaultOpenPortRule);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_Enabled", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039960  mov     [rsp+arg_8], rbx
0x180039965  mov     [rsp+arg_10], rbp
0x18003996a  push    rsi
0x18003996b  push    rdi
0x18003996c  push    r14
0x18003996e  sub     rsp, 230h
0x180039975  mov     rax, cs:__security_cookie
0x18003997c  xor     rax, rsp
0x18003997f  mov     [rsp+248h+var_28], rax
0x180039987  movzx   r14d, dx
0x18003998b  mov     rdi, rcx
0x18003998e  xor     edx, edx; Val
0x180039990  lea     rcx, [rsp+248h+var_228]; void *
0x180039995  mov     r8d, 1F8h; Size
0x18003999b  call    memset_0
0x1800399a0  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800399a4  call    cs:__imp_EnterCriticalSection
0x1800399aa  lea     rsi, [rdi+48h]
0x1800399ae  cmp     qword ptr [rsi], 0
0x1800399b2  jnz     short loc_1800399CA
0x1800399b4  mov     edx, [rdi+40h]
0x1800399b7  mov     rcx, rsi
0x1800399ba  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x1800399c0  mov     ebx, eax
0x1800399c2  test    eax, eax
0x1800399c4  js      loc_180039AA4
0x1800399ca  mov     rax, [rsi]
0x1800399cd  lea     rcx, [rsp+248h+var_228]
0x1800399d2  mov     r8d, 3
0x1800399d8  mov     edx, r8d
0x1800399db  lea     r9d, [r8+7Dh]
0x1800399df  movups  xmm0, xmmword ptr [rax]
0x1800399e2  movups  xmmword ptr [rcx], xmm0
0x1800399e5  movups  xmm1, xmmword ptr [rax+10h]
0x1800399e9  movups  xmmword ptr [rcx+10h], xmm1
0x1800399ed  movups  xmm0, xmmword ptr [rax+20h]
0x1800399f1  movups  xmmword ptr [rcx+20h], xmm0
0x1800399f5  movups  xmm1, xmmword ptr [rax+30h]
0x1800399f9  movups  xmmword ptr [rcx+30h], xmm1
0x1800399fd  movups  xmm0, xmmword ptr [rax+40h]
0x180039a01  movups  xmmword ptr [rcx+40h], xmm0
0x180039a05  movups  xmm1, xmmword ptr [rax+50h]
0x180039a09  movups  xmmword ptr [rcx+50h], xmm1
0x180039a0d  movups  xmm0, xmmword ptr [rax+60h]
0x180039a11  movups  xmmword ptr [rcx+60h], xmm0
0x180039a15  movups  xmm1, xmmword ptr [rax+70h]
0x180039a19  add     rax, r9
0x180039a1c  movups  xmmword ptr [rcx+70h], xmm1
0x180039a20  add     rcx, r9
0x180039a23  sub     rdx, 1
0x180039a27  jnz     short loc_1800399DF
0x180039a29  movups  xmm0, xmmword ptr [rax]
0x180039a2c  movups  xmmword ptr [rcx], xmm0
0x180039a2f  movups  xmm1, xmmword ptr [rax+10h]
0x180039a33  movups  xmmword ptr [rcx+10h], xmm1
0x180039a37  movups  xmm0, xmmword ptr [rax+20h]
0x180039a3b  movups  xmmword ptr [rcx+20h], xmm0
0x180039a3f  movups  xmm1, xmmword ptr [rax+30h]
0x180039a43  movups  xmmword ptr [rcx+30h], xmm1
0x180039a47  movups  xmm0, xmmword ptr [rax+40h]
0x180039a4b  movups  xmmword ptr [rcx+40h], xmm0
0x180039a4f  movups  xmm1, xmmword ptr [rax+50h]
0x180039a53  movups  xmmword ptr [rcx+50h], xmm1
0x180039a57  movups  xmm0, xmmword ptr [rax+60h]
0x180039a5b  movups  xmmword ptr [rcx+60h], xmm0
0x180039a5f  mov     rax, [rax+70h]
0x180039a63  mov     [rcx+70h], rax
0x180039a67  cmp     r14w, 0FFFFh
0x180039a6c  jnz     short loc_180039A81
0x180039a6e  or      [rsp+248h+var_104], 1
0x180039a77  mov     [rsp+248h+var_108], r8d
0x180039a7f  jmp     short loc_180039A8E
0x180039a81  mov     eax, 0FFFEh
0x180039a86  and     [rsp+248h+var_104], ax
0x180039a8e  mov     r8, [rsi]; struct _tag_FW_RULE *
0x180039a91  lea     rdx, [rsp+248h+var_228]; struct _tag_FW_RULE *
0x180039a96  mov     rcx, rdi; this
0x180039a99  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x180039a9e  mov     ebx, eax
0x180039aa0  test    eax, eax
0x180039aa2  jns     short loc_180039AB3
0x180039aa4  mov     edx, eax
0x180039aa6  lea     rcx, aFwopenportPutE; "FwOpenPort::put_Enabled"
0x180039aad  call    cs:__imp_FwReportReturnError
0x180039ab3  lea     rcx, [rdi+10h]; lpCriticalSection
0x180039ab7  call    cs:__imp_LeaveCriticalSection
0x180039abd  test    ebx, ebx
0x180039abf  jns     short loc_180039AD2
0x180039ac1  mov     edx, ebx
0x180039ac3  lea     rcx, aFwopenportPutE; "FwOpenPort::put_Enabled"
0x180039aca  call    cs:__imp_FwReportReturnError
0x180039ad0  mov     ebx, eax
0x180039ad2  mov     eax, ebx
0x180039ad4  mov     rcx, [rsp+248h+var_28]
0x180039adc  xor     rcx, rsp; StackCookie
0x180039adf  call    __security_check_cookie
0x180039ae4  lea     r11, [rsp+248h+var_18]
0x180039aec  mov     rbx, [r11+28h]
0x180039af0  mov     rbp, [r11+30h]
0x180039af4  mov     rsp, r11
0x180039af7  pop     r14
0x180039af9  pop     rdi
0x180039afa  pop     rsi
0x180039afb  retn
```

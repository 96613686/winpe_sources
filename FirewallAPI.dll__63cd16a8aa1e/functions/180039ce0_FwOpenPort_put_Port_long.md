# FwOpenPort::put_Port(long)

- ea: `0x180039ce0`
- end: `0x180039e9f`
- name: `?put_Port@FwOpenPort@@UEAAJJ@Z`
- size: `447`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800277b0`
- `0x1800284c4`
- `0x1800392c0`
- `0x180039ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039e66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039e66`
- `fwbase!FwReportReturnError` at `0x180039e5c`
- `fwbase!FwReportReturnError` at `0x180039e75`
- `fwbase!FwReportReturnError` at `0x180039e5c`
- `fwbase!FwReportReturnError` at `0x180039e75`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180039d75`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180039d75`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039d53`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x180039d53`

## string_xrefs

- `0x180039d2f`: `FwOpenPort::put_Port`

## pseudocode

```c
__int64 __fastcall FwOpenPort::put_Port(FwOpenPort *this, unsigned int a2)
{
  struct _tag_FW_RULE **v4; // rdi
  int DefaultOpenPortRule; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  struct _tag_FW_RULE *v8; // rax
  _OWORD *v9; // rdx
  __int64 v10; // rcx
  __int128 v11; // xmm1
  _BYTE v13[72]; // [rsp+20h] [rbp-248h] BYREF
  _WORD *v14; // [rsp+68h] [rbp-200h]
  int v15; // [rsp+220h] [rbp-48h] BYREF

  v15 = 0;
  memset_0(v13, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 > 0xFFFF )
  {
    v6 = -2147024809;
    goto LABEL_12;
  }
  v4 = (struct _tag_FW_RULE **)((char *)this + 72);
  if ( !*((_QWORD *)this + 9) )
  {
    DefaultOpenPortRule = CreateDefaultOpenPortRule((char *)this + 72, *((unsigned int *)this + 16));
    v6 = DefaultOpenPortRule;
    if ( DefaultOpenPortRule < 0 )
      goto LABEL_4;
  }
  FwWfProtocolToICFProtocol(*((unsigned __int16 *)*v4 + 24), &v15);
  if ( *((_DWORD *)this + 20) )
  {
    v6 = -2147024891;
LABEL_12:
    v7 = v6;
    goto LABEL_13;
  }
  v8 = *v4;
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
  v14[1] = a2;
  *v14 = a2;
  DefaultOpenPortRule = FwOpenPort::SetRule(this, (const struct _tag_FW_RULE *)v13, *v4);
  v6 = DefaultOpenPortRule;
  if ( DefaultOpenPortRule < 0 )
  {
LABEL_4:
    v7 = (unsigned int)DefaultOpenPortRule;
LABEL_13:
    FwReportReturnError("FwOpenPort::put_Port", v7);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (v6 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::put_Port", v6);
  return v6;
}

```

## disassembly

```asm
0x180039ce0  push    rbx
0x180039ce2  push    rbp
0x180039ce3  push    rsi
0x180039ce4  push    rdi
0x180039ce5  push    r14
0x180039ce7  push    r15
0x180039ce9  sub     rsp, 238h
0x180039cf0  mov     rax, cs:__security_cookie
0x180039cf7  xor     rax, rsp
0x180039cfa  mov     [rsp+268h+var_40], rax
0x180039d02  mov     r14d, edx
0x180039d05  mov     [rsp+268h+var_48], 0
0x180039d10  mov     rsi, rcx
0x180039d13  xor     edx, edx; Val
0x180039d15  lea     rcx, [rsp+268h+var_248]; void *
0x180039d1a  mov     r8d, 1F8h; Size
0x180039d20  call    memset_0
0x180039d25  lea     rcx, [rsi+10h]; lpCriticalSection
0x180039d29  call    cs:__imp_EnterCriticalSection
0x180039d2f  lea     r15, aFwopenportPutP; "FwOpenPort::put_Port"
0x180039d36  cmp     r14d, 0FFFFh
0x180039d3d  ja      loc_180039E52
0x180039d43  lea     rdi, [rsi+48h]
0x180039d47  cmp     qword ptr [rdi], 0
0x180039d4b  jnz     short loc_180039D66
0x180039d4d  mov     edx, [rsi+40h]
0x180039d50  mov     rcx, rdi
0x180039d53  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x180039d59  mov     ebx, eax
0x180039d5b  test    eax, eax
0x180039d5d  jns     short loc_180039D66
0x180039d5f  mov     edx, eax
0x180039d61  jmp     loc_180039E59
0x180039d66  mov     rcx, [rdi]
0x180039d69  lea     rdx, [rsp+268h+var_48]
0x180039d71  movzx   ecx, word ptr [rcx+30h]
0x180039d75  call    cs:__imp_FwWfProtocolToICFProtocol
0x180039d7b  cmp     dword ptr [rsi+50h], 0
0x180039d7f  jz      short loc_180039D8B
0x180039d81  mov     ebx, 80070005h
0x180039d86  jmp     loc_180039E57
0x180039d8b  mov     rax, [rdi]
0x180039d8e  lea     rdx, [rsp+268h+var_248]
0x180039d93  mov     ecx, 3
0x180039d98  lea     r8d, [rcx+7Dh]
0x180039d9c  movups  xmm0, xmmword ptr [rax]
0x180039d9f  movups  xmmword ptr [rdx], xmm0
0x180039da2  movups  xmm1, xmmword ptr [rax+10h]
0x180039da6  movups  xmmword ptr [rdx+10h], xmm1
0x180039daa  movups  xmm0, xmmword ptr [rax+20h]
0x180039dae  movups  xmmword ptr [rdx+20h], xmm0
0x180039db2  movups  xmm1, xmmword ptr [rax+30h]
0x180039db6  movups  xmmword ptr [rdx+30h], xmm1
0x180039dba  movups  xmm0, xmmword ptr [rax+40h]
0x180039dbe  movups  xmmword ptr [rdx+40h], xmm0
0x180039dc2  movups  xmm1, xmmword ptr [rax+50h]
0x180039dc6  movups  xmmword ptr [rdx+50h], xmm1
0x180039dca  movups  xmm0, xmmword ptr [rax+60h]
0x180039dce  movups  xmmword ptr [rdx+60h], xmm0
0x180039dd2  movups  xmm1, xmmword ptr [rax+70h]
0x180039dd6  add     rax, r8
0x180039dd9  movups  xmmword ptr [rdx+70h], xmm1
0x180039ddd  add     rdx, r8
0x180039de0  sub     rcx, 1
0x180039de4  jnz     short loc_180039D9C
0x180039de6  movups  xmm0, xmmword ptr [rax]
0x180039de9  mov     rcx, rsi; this
0x180039dec  movups  xmmword ptr [rdx], xmm0
0x180039def  movups  xmm1, xmmword ptr [rax+10h]
0x180039df3  movups  xmmword ptr [rdx+10h], xmm1
0x180039df7  movups  xmm0, xmmword ptr [rax+20h]
0x180039dfb  movups  xmmword ptr [rdx+20h], xmm0
0x180039dff  movups  xmm1, xmmword ptr [rax+30h]
0x180039e03  movups  xmmword ptr [rdx+30h], xmm1
0x180039e07  movups  xmm0, xmmword ptr [rax+40h]
0x180039e0b  movups  xmmword ptr [rdx+40h], xmm0
0x180039e0f  movups  xmm1, xmmword ptr [rax+50h]
0x180039e13  movups  xmmword ptr [rdx+50h], xmm1
0x180039e17  movups  xmm0, xmmword ptr [rax+60h]
0x180039e1b  movups  xmmword ptr [rdx+60h], xmm0
0x180039e1f  mov     rax, [rax+70h]
0x180039e23  mov     [rdx+70h], rax
0x180039e27  lea     rdx, [rsp+268h+var_248]; struct _tag_FW_RULE *
0x180039e2c  mov     rax, [rsp+268h+var_200]
0x180039e31  mov     [rax+2], r14w
0x180039e36  mov     rax, [rsp+268h+var_200]
0x180039e3b  mov     [rax], r14w
0x180039e3f  mov     r8, [rdi]; struct _tag_FW_RULE *
0x180039e42  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x180039e47  mov     ebx, eax
0x180039e49  test    eax, eax
0x180039e4b  jns     short loc_180039E62
0x180039e4d  jmp     loc_180039D5F
0x180039e52  mov     ebx, 80070057h
0x180039e57  mov     edx, ebx
0x180039e59  mov     rcx, r15
0x180039e5c  call    cs:__imp_FwReportReturnError
0x180039e62  lea     rcx, [rsi+10h]; lpCriticalSection
0x180039e66  call    cs:__imp_LeaveCriticalSection
0x180039e6c  test    ebx, ebx
0x180039e6e  jns     short loc_180039E7D
0x180039e70  mov     edx, ebx
0x180039e72  mov     rcx, r15
0x180039e75  call    cs:__imp_FwReportReturnError
0x180039e7b  mov     ebx, eax
0x180039e7d  mov     eax, ebx
0x180039e7f  mov     rcx, [rsp+268h+var_40]
0x180039e87  xor     rcx, rsp; StackCookie
0x180039e8a  call    __security_check_cookie
0x180039e8f  add     rsp, 238h
0x180039e96  pop     r15
0x180039e98  pop     r14
0x180039e9a  pop     rdi
0x180039e9b  pop     rsi
0x180039e9c  pop     rbp
0x180039e9d  pop     rbx
0x180039e9e  retn
```

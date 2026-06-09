# FwOpenPort::put_Port(long)

- ea: `0x18003c940`
- end: `0x18003cb24`
- name: `?put_Port@FwOpenPort@@UEAAJJ@Z`
- size: `484`
- prototype: `__int64 __fastcall(FwOpenPort *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800294b0`
- `0x18002a1f4`
- `0x18003bd9c`
- `0x18003c940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c989`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c989`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cade`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cade`
- `fwbase!FwReportReturnError` at `0x18003cace`
- `fwbase!FwReportReturnError` at `0x18003caf3`
- `fwbase!FwReportReturnError` at `0x18003cace`
- `fwbase!FwReportReturnError` at `0x18003caf3`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x18003c9e1`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x18003c9e1`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c9b9`
- `FWPolicyIOMgr!CreateDefaultOpenPortRule` at `0x18003c9b9`

## string_xrefs

- `0x18003c995`: `FwOpenPort::put_Port`

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
0x18003c940  push    rbx
0x18003c942  push    rbp
0x18003c943  push    rsi
0x18003c944  push    rdi
0x18003c945  push    r14
0x18003c947  push    r15
0x18003c949  sub     rsp, 238h
0x18003c950  mov     rax, cs:__security_cookie
0x18003c957  xor     rax, rsp
0x18003c95a  mov     [rsp+268h+var_40], rax
0x18003c962  mov     r14d, edx
0x18003c965  mov     [rsp+268h+var_48], 0
0x18003c970  mov     rsi, rcx
0x18003c973  xor     edx, edx; Val
0x18003c975  lea     rcx, [rsp+268h+var_248]; void *
0x18003c97a  mov     r8d, 1F8h; Size
0x18003c980  call    memset_0
0x18003c985  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003c989  call    cs:__imp_EnterCriticalSection
0x18003c990  nop     dword ptr [rax+rax+00h]
0x18003c995  lea     r15, aFwopenportPutP; "FwOpenPort::put_Port"
0x18003c99c  cmp     r14d, 0FFFFh
0x18003c9a3  ja      loc_18003CAC4
0x18003c9a9  lea     rdi, [rsi+48h]
0x18003c9ad  cmp     qword ptr [rdi], 0
0x18003c9b1  jnz     short loc_18003C9D2
0x18003c9b3  mov     edx, [rsi+40h]
0x18003c9b6  mov     rcx, rdi
0x18003c9b9  call    cs:__imp_?CreateDefaultOpenPortRule@@YAJPEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultOpenPortRule(_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18003c9c0  nop     dword ptr [rax+rax+00h]
0x18003c9c5  mov     ebx, eax
0x18003c9c7  test    eax, eax
0x18003c9c9  jns     short loc_18003C9D2
0x18003c9cb  mov     edx, eax
0x18003c9cd  jmp     loc_18003CACB
0x18003c9d2  mov     rcx, [rdi]
0x18003c9d5  lea     rdx, [rsp+268h+var_48]
0x18003c9dd  movzx   ecx, word ptr [rcx+30h]
0x18003c9e1  call    cs:__imp_FwWfProtocolToICFProtocol
0x18003c9e8  nop     dword ptr [rax+rax+00h]
0x18003c9ed  cmp     dword ptr [rsi+50h], 0
0x18003c9f1  jz      short loc_18003C9FD
0x18003c9f3  mov     ebx, 80070005h
0x18003c9f8  jmp     loc_18003CAC9
0x18003c9fd  mov     rax, [rdi]
0x18003ca00  lea     rdx, [rsp+268h+var_248]
0x18003ca05  mov     ecx, 3
0x18003ca0a  lea     r8d, [rcx+7Dh]
0x18003ca0e  movups  xmm0, xmmword ptr [rax]
0x18003ca11  movups  xmmword ptr [rdx], xmm0
0x18003ca14  movups  xmm1, xmmword ptr [rax+10h]
0x18003ca18  movups  xmmword ptr [rdx+10h], xmm1
0x18003ca1c  movups  xmm0, xmmword ptr [rax+20h]
0x18003ca20  movups  xmmword ptr [rdx+20h], xmm0
0x18003ca24  movups  xmm1, xmmword ptr [rax+30h]
0x18003ca28  movups  xmmword ptr [rdx+30h], xmm1
0x18003ca2c  movups  xmm0, xmmword ptr [rax+40h]
0x18003ca30  movups  xmmword ptr [rdx+40h], xmm0
0x18003ca34  movups  xmm1, xmmword ptr [rax+50h]
0x18003ca38  movups  xmmword ptr [rdx+50h], xmm1
0x18003ca3c  movups  xmm0, xmmword ptr [rax+60h]
0x18003ca40  movups  xmmword ptr [rdx+60h], xmm0
0x18003ca44  movups  xmm1, xmmword ptr [rax+70h]
0x18003ca48  add     rax, r8
0x18003ca4b  movups  xmmword ptr [rdx+70h], xmm1
0x18003ca4f  add     rdx, r8
0x18003ca52  sub     rcx, 1
0x18003ca56  jnz     short loc_18003CA0E
0x18003ca58  movups  xmm0, xmmword ptr [rax]
0x18003ca5b  mov     rcx, rsi; this
0x18003ca5e  movups  xmmword ptr [rdx], xmm0
0x18003ca61  movups  xmm1, xmmword ptr [rax+10h]
0x18003ca65  movups  xmmword ptr [rdx+10h], xmm1
0x18003ca69  movups  xmm0, xmmword ptr [rax+20h]
0x18003ca6d  movups  xmmword ptr [rdx+20h], xmm0
0x18003ca71  movups  xmm1, xmmword ptr [rax+30h]
0x18003ca75  movups  xmmword ptr [rdx+30h], xmm1
0x18003ca79  movups  xmm0, xmmword ptr [rax+40h]
0x18003ca7d  movups  xmmword ptr [rdx+40h], xmm0
0x18003ca81  movups  xmm1, xmmword ptr [rax+50h]
0x18003ca85  movups  xmmword ptr [rdx+50h], xmm1
0x18003ca89  movups  xmm0, xmmword ptr [rax+60h]
0x18003ca8d  movups  xmmword ptr [rdx+60h], xmm0
0x18003ca91  mov     rax, [rax+70h]
0x18003ca95  mov     [rdx+70h], rax
0x18003ca99  lea     rdx, [rsp+268h+var_248]; struct _tag_FW_RULE *
0x18003ca9e  mov     rax, [rsp+268h+var_200]
0x18003caa3  mov     [rax+2], r14w
0x18003caa8  mov     rax, [rsp+268h+var_200]
0x18003caad  mov     [rax], r14w
0x18003cab1  mov     r8, [rdi]; struct _tag_FW_RULE *
0x18003cab4  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x18003cab9  mov     ebx, eax
0x18003cabb  test    eax, eax
0x18003cabd  jns     short loc_18003CADA
0x18003cabf  jmp     loc_18003C9CB
0x18003cac4  mov     ebx, 80070057h
0x18003cac9  mov     edx, ebx
0x18003cacb  mov     rcx, r15
0x18003cace  call    cs:__imp_FwReportReturnError
0x18003cad5  nop     dword ptr [rax+rax+00h]
0x18003cada  lea     rcx, [rsi+10h]; lpCriticalSection
0x18003cade  call    cs:__imp_LeaveCriticalSection
0x18003cae5  nop     dword ptr [rax+rax+00h]
0x18003caea  test    ebx, ebx
0x18003caec  jns     short loc_18003CB01
0x18003caee  mov     edx, ebx
0x18003caf0  mov     rcx, r15
0x18003caf3  call    cs:__imp_FwReportReturnError
0x18003cafa  nop     dword ptr [rax+rax+00h]
0x18003caff  mov     ebx, eax
0x18003cb01  mov     eax, ebx
0x18003cb03  mov     rcx, [rsp+268h+var_40]
0x18003cb0b  xor     rcx, rsp; StackCookie
0x18003cb0e  call    __security_check_cookie
0x18003cb13  add     rsp, 238h
0x18003cb1a  pop     r15
0x18003cb1c  pop     r14
0x18003cb1e  pop     rdi
0x18003cb1f  pop     rsi
0x18003cb20  pop     rbp
0x18003cb21  pop     rbx
0x18003cb22  retn
```

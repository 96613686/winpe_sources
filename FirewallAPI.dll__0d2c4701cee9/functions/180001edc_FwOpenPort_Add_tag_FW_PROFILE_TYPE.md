# FwOpenPort::Add(_tag_FW_PROFILE_TYPE)

- ea: `0x180001edc`
- end: `0x18000209b`
- name: `?Add@FwOpenPort@@QEAAJW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `447`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180048a20`

## callees

- `0x180001edc`
- `0x1800037dc`
- `0x180009780`
- `0x18000c3f0`
- `0x18000d0f0`
- `0x1800294b0`
- `0x18003bd9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002054`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002054`
- `fwbase!FwReportReturnError` at `0x180002032`
- `fwbase!FwReportReturnError` at `0x180002069`
- `fwbase!FwReportReturnError` at `0x180002032`
- `fwbase!FwReportReturnError` at `0x180002069`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x180002005`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x180002005`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180001fe2`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180001fe2`

## string_xrefs

- `0x180001f36`: `FwOpenPort::Add`

## pseudocode

```c
__int64 __fastcall FwOpenPort::Add(__int64 a1, int a2)
{
  __int64 v4; // rdx
  signed int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  struct _tag_FW_RULE *MatchingOpenPortRule; // rax
  const struct _tag_FW_RULE *v10; // rdx
  int v11; // eax
  unsigned int v13; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v15; // [rsp+38h] [rbp-18h] BYREF
  void *v16; // [rsp+40h] [rbp-10h] BYREF

  v15 = 0;
  v14 = 0;
  v13 = 0;
  v16 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( *(_DWORD *)(a1 + 84) || (v6 = *(_QWORD *)(a1 + 72)) == 0 )
  {
    v4 = 2147549183LL;
    v5 = -2147418113;
  }
  else
  {
    *(_DWORD *)(a1 + 64) = a2;
    *(_DWORD *)(v6 + 40) = a2;
    v7 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, &v16);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 < 0 )
      goto LABEL_7;
    v8 = FWEnumFirewallRules((_DWORD)v16, 196608, *(_DWORD *)(a1 + 64), 7, (__int64)&v14, (__int64)&v15);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 < 0 )
    {
LABEL_7:
      v4 = (unsigned int)v5;
    }
    else
    {
      FwWfProtocolToICFProtocol(*(unsigned __int16 *)(*(_QWORD *)(a1 + 72) + 48LL), &v13);
      MatchingOpenPortRule = (struct _tag_FW_RULE *)FwFindMatchingOpenPortRule(
                                                      v15,
                                                      v14,
                                                      **(unsigned __int16 **)(*(_QWORD *)(a1 + 72) + 72LL),
                                                      v13);
      v10 = *(const struct _tag_FW_RULE **)(a1 + 72);
      *(_DWORD *)(a1 + 84) = 1;
      v11 = FwOpenPort::SetRule((FwOpenPort *)a1, v10, MatchingOpenPortRule);
      v5 = v11;
      if ( v11 >= 0 )
        goto LABEL_14;
      v4 = (unsigned int)v11;
    }
  }
  FwReportReturnError("FwOpenPort::Add", v4);
LABEL_14:
  FWFreeFirewallRules(v15);
  CloseLocalPolicyStore(v16);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::Add", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180001edc  mov     [rsp-18h+arg_8], rbx
0x180001ee1  mov     [rsp-18h+arg_10], rsi
0x180001ee6  push    rbp
0x180001ee7  push    rdi
0x180001ee8  push    r15
0x180001eea  mov     rbp, rsp
0x180001eed  sub     rsp, 50h
0x180001ef1  mov     rax, cs:__security_cookie
0x180001ef8  xor     rax, rsp
0x180001efb  mov     [rbp+var_8], rax
0x180001eff  mov     rdi, rcx
0x180001f02  mov     [rbp+var_18], 0
0x180001f0a  add     rcx, 10h; lpCriticalSection
0x180001f0e  mov     [rbp+var_1C], 0
0x180001f15  mov     ebx, edx
0x180001f17  mov     [rbp+var_20], 0
0x180001f1e  mov     [rbp+var_10], 0
0x180001f26  call    cs:__imp_EnterCriticalSection
0x180001f2d  nop     dword ptr [rax+rax+00h]
0x180001f32  cmp     dword ptr [rdi+54h], 0
0x180001f36  lea     r15, aFwopenportAdd; "FwOpenPort::Add"
0x180001f3d  jz      short loc_180001F4B
0x180001f3f  mov     edx, 8000FFFFh
0x180001f44  mov     ebx, edx
0x180001f46  jmp     loc_18000202F
0x180001f4b  mov     rax, [rdi+48h]
0x180001f4f  test    rax, rax
0x180001f52  jz      short loc_180001F3F
0x180001f54  xor     edx, edx
0x180001f56  mov     [rdi+40h], ebx
0x180001f59  mov     [rax+28h], ebx
0x180001f5c  mov     ecx, 221h
0x180001f61  lea     rax, [rbp+var_10]
0x180001f65  mov     [rsp+50h+var_28], rax
0x180001f6a  lea     r9d, [rdx+1]
0x180001f6e  mov     dword ptr [rsp+50h+var_30], 0
0x180001f76  lea     r8d, [rdx+2]
0x180001f7a  call    FWOpenPolicyStore
0x180001f7f  mov     ebx, eax
0x180001f81  test    eax, eax
0x180001f83  jle     short loc_180001F8E
0x180001f85  movzx   ebx, ax
0x180001f88  or      ebx, 80070000h
0x180001f8e  test    ebx, ebx
0x180001f90  jns     short loc_180001F99
0x180001f92  mov     edx, ebx
0x180001f94  jmp     loc_18000202F
0x180001f99  mov     r8d, [rdi+40h]
0x180001f9d  lea     rax, [rbp+var_18]
0x180001fa1  mov     rcx, [rbp+var_10]
0x180001fa5  mov     r9d, 7
0x180001fab  mov     [rsp+50h+var_28], rax
0x180001fb0  mov     edx, 30000h
0x180001fb5  lea     rax, [rbp+var_1C]
0x180001fb9  mov     [rsp+50h+var_30], rax
0x180001fbe  call    FWEnumFirewallRules
0x180001fc3  mov     ebx, eax
0x180001fc5  test    eax, eax
0x180001fc7  jle     short loc_180001FD2
0x180001fc9  movzx   ebx, ax
0x180001fcc  or      ebx, 80070000h
0x180001fd2  test    ebx, ebx
0x180001fd4  js      short loc_180001F92
0x180001fd6  mov     rcx, [rdi+48h]
0x180001fda  lea     rdx, [rbp+var_20]
0x180001fde  movzx   ecx, word ptr [rcx+30h]
0x180001fe2  call    cs:__imp_FwWfProtocolToICFProtocol
0x180001fe9  nop     dword ptr [rax+rax+00h]
0x180001fee  mov     rax, [rdi+48h]
0x180001ff2  mov     r9d, [rbp+var_20]
0x180001ff6  mov     rcx, [rbp+var_18]
0x180001ffa  mov     rdx, [rax+48h]
0x180001ffe  movzx   r8d, word ptr [rdx]
0x180002002  mov     edx, [rbp+var_1C]
0x180002005  call    cs:__imp_FwFindMatchingOpenPortRule
0x18000200c  nop     dword ptr [rax+rax+00h]
0x180002011  mov     rdx, [rdi+48h]; struct _tag_FW_RULE *
0x180002015  mov     rcx, rdi; this
0x180002018  mov     r8, rax; struct _tag_FW_RULE *
0x18000201b  mov     dword ptr [rdi+54h], 1
0x180002022  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x180002027  mov     ebx, eax
0x180002029  test    eax, eax
0x18000202b  jns     short loc_18000203E
0x18000202d  mov     edx, eax
0x18000202f  mov     rcx, r15
0x180002032  call    cs:__imp_FwReportReturnError
0x180002039  nop     dword ptr [rax+rax+00h]
0x18000203e  mov     rcx, [rbp+var_18]
0x180002042  call    FWFreeFirewallRules
0x180002047  mov     rcx, [rbp+var_10]; void *
0x18000204b  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180002050  lea     rcx, [rdi+10h]; lpCriticalSection
0x180002054  call    cs:__imp_LeaveCriticalSection
0x18000205b  nop     dword ptr [rax+rax+00h]
0x180002060  test    ebx, ebx
0x180002062  jns     short loc_180002077
0x180002064  mov     edx, ebx
0x180002066  mov     rcx, r15
0x180002069  call    cs:__imp_FwReportReturnError
0x180002070  nop     dword ptr [rax+rax+00h]
0x180002075  mov     ebx, eax
0x180002077  mov     eax, ebx
0x180002079  mov     rcx, [rbp+var_8]
0x18000207d  xor     rcx, rsp; StackCookie
0x180002080  call    __security_check_cookie
0x180002085  lea     r11, [rsp+50h+var_s0]
0x18000208a  mov     rbx, [r11+28h]
0x18000208e  mov     rsi, [r11+30h]
0x180002092  mov     rsp, r11
0x180002095  pop     r15
0x180002097  pop     rdi
0x180002098  pop     rbp
0x180002099  retn
```

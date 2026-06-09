# FwOpenPort::Add(_tag_FW_PROFILE_TYPE)

- ea: `0x180001e58`
- end: `0x180001ff2`
- name: `?Add@FwOpenPort@@QEAAJW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800453d0`

## callees

- `0x180001e58`
- `0x180003520`
- `0x180009080`
- `0x18000b8c0`
- `0x18000c560`
- `0x1800277b0`
- `0x1800392c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ea2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ea2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001fb8`
- `fwbase!FwReportReturnError` at `0x180001f9c`
- `fwbase!FwReportReturnError` at `0x180001fc7`
- `fwbase!FwReportReturnError` at `0x180001f9c`
- `fwbase!FwReportReturnError` at `0x180001fc7`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x180001f75`
- `FWPolicyIOMgr!FwFindMatchingOpenPortRule` at `0x180001f75`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180001f58`
- `FWPolicyIOMgr!FwWfProtocolToICFProtocol` at `0x180001f58`

## string_xrefs

- `0x180001eac`: `FwOpenPort::Add`

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
0x180001e58  mov     [rsp-18h+arg_8], rbx
0x180001e5d  mov     [rsp-18h+arg_10], rsi
0x180001e62  push    rbp
0x180001e63  push    rdi
0x180001e64  push    r15
0x180001e66  mov     rbp, rsp
0x180001e69  sub     rsp, 50h
0x180001e6d  mov     rax, cs:__security_cookie
0x180001e74  xor     rax, rsp
0x180001e77  mov     [rbp+var_8], rax
0x180001e7b  mov     rdi, rcx
0x180001e7e  mov     [rbp+var_18], 0
0x180001e86  add     rcx, 10h; lpCriticalSection
0x180001e8a  mov     [rbp+var_1C], 0
0x180001e91  mov     ebx, edx
0x180001e93  mov     [rbp+var_20], 0
0x180001e9a  mov     [rbp+var_10], 0
0x180001ea2  call    cs:__imp_EnterCriticalSection
0x180001ea8  cmp     dword ptr [rdi+54h], 0
0x180001eac  lea     r15, aFwopenportAdd; "FwOpenPort::Add"
0x180001eb3  jz      short loc_180001EC1
0x180001eb5  mov     edx, 8000FFFFh
0x180001eba  mov     ebx, edx
0x180001ebc  jmp     loc_180001F99
0x180001ec1  mov     rax, [rdi+48h]
0x180001ec5  test    rax, rax
0x180001ec8  jz      short loc_180001EB5
0x180001eca  xor     edx, edx
0x180001ecc  mov     [rdi+40h], ebx
0x180001ecf  mov     [rax+28h], ebx
0x180001ed2  mov     ecx, 221h
0x180001ed7  lea     rax, [rbp+var_10]
0x180001edb  mov     [rsp+50h+var_28], rax
0x180001ee0  lea     r9d, [rdx+1]
0x180001ee4  mov     dword ptr [rsp+50h+var_30], 0
0x180001eec  lea     r8d, [rdx+2]
0x180001ef0  call    FWOpenPolicyStore
0x180001ef5  mov     ebx, eax
0x180001ef7  test    eax, eax
0x180001ef9  jle     short loc_180001F04
0x180001efb  movzx   ebx, ax
0x180001efe  or      ebx, 80070000h
0x180001f04  test    ebx, ebx
0x180001f06  jns     short loc_180001F0F
0x180001f08  mov     edx, ebx
0x180001f0a  jmp     loc_180001F99
0x180001f0f  mov     r8d, [rdi+40h]
0x180001f13  lea     rax, [rbp+var_18]
0x180001f17  mov     rcx, [rbp+var_10]
0x180001f1b  mov     r9d, 7
0x180001f21  mov     [rsp+50h+var_28], rax
0x180001f26  mov     edx, 30000h
0x180001f2b  lea     rax, [rbp+var_1C]
0x180001f2f  mov     [rsp+50h+var_30], rax
0x180001f34  call    FWEnumFirewallRules
0x180001f39  mov     ebx, eax
0x180001f3b  test    eax, eax
0x180001f3d  jle     short loc_180001F48
0x180001f3f  movzx   ebx, ax
0x180001f42  or      ebx, 80070000h
0x180001f48  test    ebx, ebx
0x180001f4a  js      short loc_180001F08
0x180001f4c  mov     rcx, [rdi+48h]
0x180001f50  lea     rdx, [rbp+var_20]
0x180001f54  movzx   ecx, word ptr [rcx+30h]
0x180001f58  call    cs:__imp_FwWfProtocolToICFProtocol
0x180001f5e  mov     rax, [rdi+48h]
0x180001f62  mov     r9d, [rbp+var_20]
0x180001f66  mov     rcx, [rbp+var_18]
0x180001f6a  mov     rdx, [rax+48h]
0x180001f6e  movzx   r8d, word ptr [rdx]
0x180001f72  mov     edx, [rbp+var_1C]
0x180001f75  call    cs:__imp_FwFindMatchingOpenPortRule
0x180001f7b  mov     rdx, [rdi+48h]; struct _tag_FW_RULE *
0x180001f7f  mov     rcx, rdi; this
0x180001f82  mov     r8, rax; struct _tag_FW_RULE *
0x180001f85  mov     dword ptr [rdi+54h], 1
0x180001f8c  call    ?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z; FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)
0x180001f91  mov     ebx, eax
0x180001f93  test    eax, eax
0x180001f95  jns     short loc_180001FA2
0x180001f97  mov     edx, eax
0x180001f99  mov     rcx, r15
0x180001f9c  call    cs:__imp_FwReportReturnError
0x180001fa2  mov     rcx, [rbp+var_18]
0x180001fa6  call    FWFreeFirewallRules
0x180001fab  mov     rcx, [rbp+var_10]; void *
0x180001faf  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180001fb4  lea     rcx, [rdi+10h]; lpCriticalSection
0x180001fb8  call    cs:__imp_LeaveCriticalSection
0x180001fbe  test    ebx, ebx
0x180001fc0  jns     short loc_180001FCF
0x180001fc2  mov     edx, ebx
0x180001fc4  mov     rcx, r15
0x180001fc7  call    cs:__imp_FwReportReturnError
0x180001fcd  mov     ebx, eax
0x180001fcf  mov     eax, ebx
0x180001fd1  mov     rcx, [rbp+var_8]
0x180001fd5  xor     rcx, rsp; StackCookie
0x180001fd8  call    __security_check_cookie
0x180001fdd  lea     r11, [rsp+50h+var_s0]
0x180001fe2  mov     rbx, [r11+28h]
0x180001fe6  mov     rsi, [r11+30h]
0x180001fea  mov     rsp, r11
0x180001fed  pop     r15
0x180001fef  pop     rdi
0x180001ff0  pop     rbp
0x180001ff1  retn
```

# FwStringToAddresses

- ea: `0x180021710`
- end: `0x1800217e8`
- name: `FwStringToAddresses`
- size: `216`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005e0c`
- `0x180021710`
- `0x1800294b0`

## import_xrefs

- `fwbase!FwBaseFree` at `0x1800217c1`
- `fwbase!FwBaseFree` at `0x1800217c1`
- `fwbase!FwStringCopy` at `0x18002173a`
- `fwbase!FwStringCopy` at `0x18002173a`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180021774`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180021774`

## pseudocode

```c
__int64 __fastcall FwStringToAddresses(__int64 a1, __int64 a2)
{
  int v3; // ebx
  FwPolicy2 *v4; // rcx
  __int64 v5; // rdx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  v3 = FwStringCopy(a1, &v7);
  if ( v3 >= 0 )
  {
    v3 = StringToOpenPortOrAuthAppAddress(v7, a2);
    if ( v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 569;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 568;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, (unsigned int)v3);
    }
  }
  if ( v7 )
    FwBaseFree(v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180021710  mov     [rsp+arg_10], rbx
0x180021715  push    rdi
0x180021716  sub     rsp, 30h
0x18002171a  mov     rax, cs:__security_cookie
0x180021721  xor     rax, rsp
0x180021724  mov     [rsp+38h+var_10], rax
0x180021729  mov     rdi, rdx
0x18002172c  mov     [rsp+38h+var_18], 0
0x180021735  lea     rdx, [rsp+38h+var_18]
0x18002173a  call    cs:__imp_FwStringCopy
0x180021741  nop     dword ptr [rax+rax+00h]
0x180021746  mov     ebx, eax
0x180021748  test    eax, eax
0x18002174a  jns     short loc_18002176C
0x18002174c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021753  lea     rax, WPP_GLOBAL_Control
0x18002175a  cmp     rcx, rax
0x18002175d  jz      short loc_1800217B7
0x18002175f  test    byte ptr [rcx+1Ch], 1
0x180021763  jz      short loc_1800217B7
0x180021765  mov     edx, 238h
0x18002176a  jmp     short loc_1800217A4
0x18002176c  mov     rcx, [rsp+38h+var_18]
0x180021771  mov     rdx, rdi
0x180021774  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x18002177b  nop     dword ptr [rax+rax+00h]
0x180021780  mov     ebx, eax
0x180021782  test    eax, eax
0x180021784  jns     short loc_1800217B7
0x180021786  mov     rcx, cs:WPP_GLOBAL_Control
0x18002178d  lea     rax, WPP_GLOBAL_Control
0x180021794  cmp     rcx, rax
0x180021797  jz      short loc_1800217B7
0x180021799  test    byte ptr [rcx+1Ch], 1
0x18002179d  jz      short loc_1800217B7
0x18002179f  mov     edx, 239h
0x1800217a4  mov     rcx, [rcx+10h]
0x1800217a8  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800217af  mov     r9d, ebx
0x1800217b2  call    WPP_SF_d
0x1800217b7  mov     rcx, [rsp+38h+var_18]
0x1800217bc  test    rcx, rcx
0x1800217bf  jz      short loc_1800217CD
0x1800217c1  call    cs:__imp_FwBaseFree
0x1800217c8  nop     dword ptr [rax+rax+00h]
0x1800217cd  mov     eax, ebx
0x1800217cf  mov     rcx, [rsp+38h+var_10]
0x1800217d4  xor     rcx, rsp; StackCookie
0x1800217d7  call    __security_check_cookie
0x1800217dc  mov     rbx, [rsp+38h+arg_10]
0x1800217e1  add     rsp, 30h
0x1800217e5  pop     rdi
0x1800217e6  retn
```

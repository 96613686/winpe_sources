# CBdeSvcDE::NotifyGPUpdate(void)

- ea: `0x18002dd88`
- end: `0x18002df16`
- name: `?NotifyGPUpdate@CBdeSvcDE@@SAJXZ`
- size: `398`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18003c780`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000a010`
- `0x18002b6ac`
- `0x18002dd88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002def7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002def7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dda1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dda1`

## string_xrefs

- `0x18002deac`: `WorkerThreadLauncher`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CBdeSvcDE::NotifyGPUpdate(void)
{
  PVOID *v0; // rcx
  unsigned int v1; // ebx
  int v2; // eax
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  AcquireSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( CBdeSvcDE::s_Instance )
  {
    if ( !*((_BYTE *)CBdeSvcDE::s_Instance + 4)
      || !*(_BYTE *)CBdeSvcDE::s_Instance
      || !*((_QWORD *)CBdeSvcDE::s_Instance + 18) )
    {
      v1 = 0;
      goto LABEL_20;
    }
    v2 = WorkerThreadLauncher((__int64)CBdeSvcDE::NotifyGPUpdate_Thread, 0, 7, 0);
    v1 = v2;
    if ( v2 > 0 )
      v1 = (unsigned __int16)v2 | 0x80070000;
    v0 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v1);
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (v1 & 0x80000000) == 0 )
      goto LABEL_20;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x15F,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v1,
      (int)"WorkerThreadLauncher",
      v4);
    goto LABEL_8;
  }
  v1 = -2147024846;
  if ( v0 == &WPP_GLOBAL_Control )
    goto LABEL_23;
  if ( (*((_BYTE *)v0 + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      v0[2],
      (unsigned int)((_DWORD)CBdeSvcDE::s_Instance + 26),
      &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
      2147942450LL);
LABEL_8:
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_(v0[2], 28, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
LABEL_23:
  ReleaseSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  return v1;
}

```

## disassembly

```asm
0x18002dd88  mov     [rsp+arg_8], rbx
0x18002dd8d  mov     [rsp+arg_10], rbp
0x18002dd92  push    rsi
0x18002dd93  sub     rsp, 30h
0x18002dd97  lea     rbp, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CBdeSvcDE::s_InstanceSrwLock
0x18002dd9e  mov     rcx, rbp; SRWLock
0x18002dda1  call    cs:__imp_AcquireSRWLockShared
0x18002dda8  nop     dword ptr [rax+rax+00h]
0x18002ddad  mov     [rsp+38h+arg_0], rbp
0x18002ddb2  lea     rsi, WPP_GLOBAL_Control
0x18002ddb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddc0  cmp     rcx, rsi
0x18002ddc3  jz      short loc_18002DDE7
0x18002ddc5  test    byte ptr [rcx+1Ch], 20h
0x18002ddc9  jz      short loc_18002DDE7
0x18002ddcb  mov     edx, 19h
0x18002ddd0  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002ddd7  mov     rcx, [rcx+10h]
0x18002dddb  call    WPP_SF_
0x18002dde0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dde7  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x18002ddee  test    rax, rax
0x18002ddf1  jnz     short loc_18002DE2D
0x18002ddf3  mov     ebx, 80070032h
0x18002ddf8  cmp     rcx, rsi
0x18002ddfb  jz      loc_18002DEF4
0x18002de01  test    byte ptr [rcx+1Ch], 40h
0x18002de05  jz      loc_18002DED3
0x18002de0b  lea     edx, [rax+1Ah]
0x18002de0e  mov     r9d, ebx
0x18002de11  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002de18  mov     rcx, [rcx+10h]
0x18002de1c  call    WPP_SF_d
0x18002de21  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de28  jmp     loc_18002DED3
0x18002de2d  cmp     byte ptr [rax+4], 0
0x18002de31  jz      loc_18002DED1
0x18002de37  cmp     byte ptr [rax], 0
0x18002de3a  jz      loc_18002DED1
0x18002de40  cmp     qword ptr [rax+90h], 0
0x18002de48  jz      loc_18002DED1
0x18002de4e  xor     r9d, r9d
0x18002de51  xor     edx, edx
0x18002de53  lea     r8d, [r9+7]
0x18002de57  lea     rcx, ?NotifyGPUpdate_Thread@CBdeSvcDE@@CAIPEAX@Z; CBdeSvcDE::NotifyGPUpdate_Thread(void *)
0x18002de5e  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z; WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)
0x18002de63  mov     ebx, eax
0x18002de65  test    eax, eax
0x18002de67  jle     short loc_18002DE72
0x18002de69  movzx   ebx, ax
0x18002de6c  or      ebx, 80070000h
0x18002de72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de79  cmp     rcx, rsi
0x18002de7c  jz      short loc_18002DEA3
0x18002de7e  test    byte ptr [rcx+1Ch], 40h
0x18002de82  jz      short loc_18002DEA3
0x18002de84  mov     edx, 1Bh
0x18002de89  mov     r9d, ebx
0x18002de8c  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002de93  mov     rcx, [rcx+10h]
0x18002de97  call    WPP_SF_d
0x18002de9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dea3  test    ebx, ebx
0x18002dea5  jns     short loc_18002DED3
0x18002dea7  mov     rcx, [rsp+38h]; this
0x18002deac  lea     rax, aWorkerthreadla; "WorkerThreadLauncher"
0x18002deb3  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002deb8  mov     r9d, ebx; char *
0x18002debb  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18002dec2  mov     edx, 15Fh; void *
0x18002dec7  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002decc  jmp     loc_18002DE21
0x18002ded1  xor     ebx, ebx
0x18002ded3  cmp     rcx, rsi
0x18002ded6  jz      short loc_18002DEF4
0x18002ded8  test    byte ptr [rcx+1Ch], 20h
0x18002dedc  jz      short loc_18002DEF4
0x18002dede  mov     edx, 1Ch
0x18002dee3  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002deea  mov     rcx, [rcx+10h]
0x18002deee  call    WPP_SF_
0x18002def3  nop
0x18002def4  mov     rcx, rbp; SRWLock
0x18002def7  call    cs:__imp_ReleaseSRWLockShared
0x18002defe  nop     dword ptr [rax+rax+00h]
0x18002df03  mov     eax, ebx
0x18002df05  mov     rbx, [rsp+38h+arg_8]
0x18002df0a  mov     rbp, [rsp+38h+arg_10]
0x18002df0f  add     rsp, 30h
0x18002df13  pop     rsi
0x18002df14  retn
```

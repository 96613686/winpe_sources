# Wns::ClientRegistration::Add(unsigned __int64,IConnectionManagerCallbacksPrivate *)

- ea: `0x180004e24`
- end: `0x180004f26`
- name: `?Add@ClientRegistration@Wns@@QEAA?AVRegistrationToken@2@_KPEAUIConnectionManagerCallbacksPrivate@@@Z`
- size: `258`
- prototype: `unsigned __int64 *__fastcall(RTL_SRWLOCK *, unsigned __int64 *, unsigned __int64, struct IConnectionManagerCallbacksPrivate *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180004d50`
- `0x18002e2c8`

## callees

- `0x1800031e0`
- `0x180004e24`
- `0x180006144`
- `0x180015c50`
- `0x180026adc`
- `0x18002de0c`
- `0x18002df88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e69`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e69`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f07`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int64 *__fastcall Wns::ClientRegistration::Add(
        RTL_SRWLOCK *a1,
        unsigned __int64 *a2,
        unsigned __int64 a3,
        struct IConnectionManagerCallbacksPrivate *a4)
{
  unsigned __int64 v5; // rsi
  Wns::Callback *v8; // rax
  __int64 v9; // rbx
  PVOID v10; // r12
  _QWORD *Ptr; // rcx
  _QWORD *v12; // rax
  _BYTE *v13; // rbx
  PVOID v15; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  char v17[12]; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+3Ch] [rbp-14h]
  unsigned __int64 v19; // [rsp+A0h] [rbp+50h] BYREF

  v19 = a3;
  v5 = a3;
  v8 = (Wns::Callback *)operator new(0x48u);
  v9 = Wns::Callback::Callback(v8, a4);
  AcquireSRWLockExclusive(a1 + 1);
  v10 = ++a1[2].Ptr;
  v15 = v10;
  v16 = v9;
  Ptr = a1[3].Ptr;
  v12 = (_QWORD *)Ptr[1];
  v18 = 0;
  v13 = Ptr;
  while ( !*((_BYTE *)v12 + 25) )
  {
    if ( v12[4] >= v5 )
    {
      v13 = v12;
      v12 = (_QWORD *)*v12;
    }
    else
    {
      v12 = (_QWORD *)v12[2];
    }
  }
  if ( v13 == (_BYTE *)Ptr || v13[25] || v5 < *((_QWORD *)v13 + 4) )
  {
    ((void (__fastcall *)(RTL_SRWLOCK *, char *, unsigned __int64 *, PVOID *))std::_Tree<std::_Tmap_traits<unsigned __int64,Wns::RegistrationEntry,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Wns::RegistrationEntry>>,0>>::_Emplace<unsigned __int64,Wns::RegistrationEntry>)(
      &a1[3],
      v17,
      &v19,
      &v15);
    v5 = v19;
  }
  else
  {
    WnsCPLog::WnsCMUserSessionProxyReplaced<unsigned __int64 &>(&v19);
    std::swap<Wns::RegistrationEntry,0>(v13 + 40, &v15);
  }
  std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>(&v16);
  if ( a1 != (RTL_SRWLOCK *)-8LL )
    ReleaseSRWLockExclusive(a1 + 1);
  *a2 = v5;
  a2[1] = (unsigned __int64)v10;
  return a2;
}

```

## disassembly

```asm
0x180004e24  mov     [rsp-38h+arg_10], r8
0x180004e29  push    rbp
0x180004e2a  push    rbx
0x180004e2b  push    rsi
0x180004e2c  push    rdi
0x180004e2d  push    r12
0x180004e2f  push    r14
0x180004e31  push    r15
0x180004e33  mov     rbp, rsp
0x180004e36  sub     rsp, 50h
0x180004e3a  mov     rbx, r9
0x180004e3d  mov     rsi, r8
0x180004e40  mov     r14, rdx
0x180004e43  mov     rdi, rcx
0x180004e46  mov     ecx, 48h ; 'H'; Size
0x180004e4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004e50  mov     [rbp+arg_0], rax
0x180004e54  mov     rdx, rbx; struct IConnectionManagerCallbacksPrivate *
0x180004e57  mov     rcx, rax; this
0x180004e5a  call    ??0Callback@Wns@@QEAA@PEAUIConnectionManagerCallbacksPrivate@@@Z; Wns::Callback::Callback(IConnectionManagerCallbacksPrivate *)
0x180004e5f  mov     rbx, rax
0x180004e62  lea     r15, [rdi+8]
0x180004e66  mov     rcx, r15; SRWLock
0x180004e69  call    cs:__imp_AcquireSRWLockExclusive
0x180004e6f  mov     [rbp+arg_0], r15
0x180004e73  inc     qword ptr [rdi+10h]
0x180004e77  mov     r12, [rdi+10h]
0x180004e7b  mov     [rbp+var_30], r12
0x180004e7f  mov     [rbp+arg_8], 0
0x180004e87  mov     [rbp+var_28], rbx
0x180004e8b  mov     rcx, [rdi+18h]
0x180004e8f  mov     rax, [rcx+8]
0x180004e93  xor     edx, edx
0x180004e95  mov     [rbp+var_14], edx
0x180004e98  mov     rbx, rcx
0x180004e9b  jmp     short loc_180004EAF
0x180004e9d  cmp     [rax+20h], rsi
0x180004ea1  jnb     short loc_180004EA9
0x180004ea3  mov     rax, [rax+10h]
0x180004ea7  jmp     short loc_180004EAF
0x180004ea9  mov     rbx, rax
0x180004eac  mov     rax, [rax]
0x180004eaf  cmp     [rax+19h], dl
0x180004eb2  jz      short loc_180004E9D
0x180004eb4  cmp     rbx, rcx
0x180004eb7  jz      short loc_180004EDC
0x180004eb9  cmp     [rbx+19h], dl
0x180004ebc  jnz     short loc_180004EDC
0x180004ebe  cmp     rsi, [rbx+20h]
0x180004ec2  jb      short loc_180004EDC
0x180004ec4  lea     rcx, [rbp+arg_10]
0x180004ec8  call    ??$WnsCMUserSessionProxyReplaced@AEA_K@WnsCPLog@@SAXAEA_K@Z; WnsCPLog::WnsCMUserSessionProxyReplaced<unsigned __int64 &>(unsigned __int64 &)
0x180004ecd  lea     rcx, [rbx+28h]
0x180004ed1  lea     rdx, [rbp+var_30]
0x180004ed5  call    ??$swap@VRegistrationEntry@Wns@@$0A@@std@@YAXAEAVRegistrationEntry@Wns@@0@Z; std::swap<Wns::RegistrationEntry,0>(Wns::RegistrationEntry &,Wns::RegistrationEntry &)
0x180004eda  jmp     short loc_180004EF5
0x180004edc  lea     r9, [rbp+var_30]
0x180004ee0  lea     r8, [rbp+arg_10]
0x180004ee4  lea     rdx, [rbp+var_20]
0x180004ee8  lea     rcx, [rdi+18h]
0x180004eec  call    ??$_Emplace@_KVRegistrationEntry@Wns@@@?$_Tree@V?$_Tmap_traits@_KVRegistrationEntry@Wns@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KVRegistrationEntry@Wns@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KVRegistrationEntry@Wns@@@std@@PEAX@std@@_N@1@$$QEA_K$$QEAVRegistrationEntry@Wns@@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,Wns::RegistrationEntry,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Wns::RegistrationEntry>>,0>>::_Emplace<unsigned __int64,Wns::RegistrationEntry>(unsigned __int64 &&,Wns::RegistrationEntry &&)
0x180004ef1  mov     rsi, [rbp+arg_10]
0x180004ef5  lea     rcx, [rbp+var_28]
0x180004ef9  call    ??1?$unique_ptr@UCallback@Wns@@U?$default_delete@UCallback@Wns@@@std@@@std@@QEAA@XZ; std::unique_ptr<Wns::Callback>::~unique_ptr<Wns::Callback>(void)
0x180004efe  nop
0x180004eff  test    r15, r15
0x180004f02  jz      short loc_180004F0D
0x180004f04  mov     rcx, r15; SRWLock
0x180004f07  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f0d  mov     [r14], rsi
0x180004f10  mov     [r14+8], r12
0x180004f14  mov     rax, r14
0x180004f17  add     rsp, 50h
0x180004f1b  pop     r15
0x180004f1d  pop     r14
0x180004f1f  pop     r12
0x180004f21  pop     rdi
0x180004f22  pop     rsi
0x180004f23  pop     rbx
0x180004f24  pop     rbp
0x180004f25  retn
```

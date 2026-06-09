# CTnoCfgMgrTransaction::CTnoCfgMgrTransaction(CTnoCfgMgr *)

- ea: `0x180029e30`
- end: `0x180029fa0`
- name: `??0CTnoCfgMgrTransaction@@QEAA@PEAVCTnoCfgMgr@@@Z`
- size: `368`
- prototype: `CTnoCfgMgrTransaction *__fastcall(CTnoCfgMgrTransaction *__hidden this, struct CTnoCfgMgr *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022dc0`

## callees

- `0x1800024a4`
- `0x180008290`
- `0x180018efc`
- `0x180020278`
- `0x180029da4`
- `0x180029e30`
- `0x18002a878`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f41`
- `ktmw32!CreateTransaction` at `0x180029e9f`
- `ktmw32!CreateTransaction` at `0x180029e9f`

## string_xrefs

- `0x180029f93`: `CTnoCfgMgrTransaction::CTnoCfgMgrTransaction CreateTransaction`

## pseudocode

```c
CTnoCfgMgrTransaction *__fastcall CTnoCfgMgrTransaction::CTnoCfgMgrTransaction(
        CTnoCfgMgrTransaction *this,
        struct CTnoCfgMgr *a2)
{
  char *Transaction; // rbx
  CRegistryContextTransacted *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  CRegistryContextTransacted *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  signed int LastError; // ebx

  *(_QWORD *)this = &CTnoCfgMgrTransaction::`vftable';
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = &ObjectHandle::`vftable';
  *((_QWORD *)this + 5) = 0;
  Transaction = (char *)CreateTransaction(0, 0, 1u, 0, 0, 0, 0);
  if ( (unsigned __int64)(Transaction - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        10,
        WPP_36d5d5f09d763694b71bd6725b4e7cf3_Traceguids,
        (unsigned int)LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SystemError::ThrowHelper(L"CTnoCfgMgrTransaction::CTnoCfgMgrTransaction CreateTransaction", LastError);
  }
  ObjectHandle::Close((CTnoCfgMgrTransaction *)((char *)this + 32));
  *((_QWORD *)this + 5) = Transaction;
  v4 = (CRegistryContextTransacted *)operator new(0x28u);
  if ( v4 )
    v4 = CRegistryContextTransacted::CRegistryContextTransacted(
           v4,
           Transaction,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist");
  std::auto_ptr<TnoHashKey>::reset((char *)this + 16, v4, v5, v6);
  v7 = (CRegistryContextTransacted *)operator new(0x28u);
  if ( v7 )
    v7 = CRegistryContextTransacted::CRegistryContextTransacted(
           v7,
           Transaction,
           L"Software\\Policies\\Microsoft\\PeerDist");
  std::auto_ptr<TnoHashKey>::reset((char *)this + 24, v7, v8, v9);
  return this;
}

```

## disassembly

```asm
0x180029e30  mov     r11, rsp
0x180029e33  mov     [r11+18h], rbx
0x180029e37  mov     [r11+20h], rsi
0x180029e3b  mov     [r11+8], rcx
0x180029e3f  push    rdi
0x180029e40  push    r14
0x180029e42  push    r15
0x180029e44  sub     rsp, 40h
0x180029e48  mov     rdi, rcx
0x180029e4b  lea     rax, ??_7CTnoCfgMgrTransaction@@6B@; const CTnoCfgMgrTransaction::`vftable'
0x180029e52  mov     [rcx], rax
0x180029e55  mov     [rcx+8], rdx
0x180029e59  mov     qword ptr [rcx+10h], 0
0x180029e61  mov     qword ptr [rcx+18h], 0
0x180029e69  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180029e70  mov     [rcx+20h], rax
0x180029e74  mov     qword ptr [rcx+28h], 0
0x180029e7c  mov     qword ptr [r11-28h], 0
0x180029e84  mov     [rsp+58h+Timeout], 0; Timeout
0x180029e8c  mov     [rsp+58h+IsolationFlags], 0; IsolationFlags
0x180029e94  xor     r9d, r9d; IsolationLevel
0x180029e97  xor     edx, edx; UOW
0x180029e99  xor     ecx, ecx; lpTransactionAttributes
0x180029e9b  lea     r8d, [r9+1]; CreateOptions
0x180029e9f  call    cs:__imp_CreateTransaction
0x180029ea5  mov     rbx, rax
0x180029ea8  lea     rcx, [rax-1]
0x180029eac  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180029eb0  ja      loc_180029F41
0x180029eb6  lea     rcx, [rdi+20h]; this
0x180029eba  call    ?Close@ObjectHandle@@QEAAXXZ; ObjectHandle::Close(void)
0x180029ebf  mov     [rdi+28h], rbx
0x180029ec3  mov     esi, 28h ; '('
0x180029ec8  mov     ecx, esi; Size
0x180029eca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029ecf  mov     [rsp+58h+arg_8], rax
0x180029ed4  test    rax, rax
0x180029ed7  jz      short loc_180029EEC
0x180029ed9  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x180029ee0  mov     rdx, rbx; void *
0x180029ee3  mov     rcx, rax; this
0x180029ee6  call    ??0CRegistryContextTransacted@@QEAA@PEAXPEBG@Z; CRegistryContextTransacted::CRegistryContextTransacted(void *,ushort const *)
0x180029eeb  nop
0x180029eec  mov     rdx, rax
0x180029eef  lea     rcx, [rdi+10h]
0x180029ef3  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180029ef8  mov     rcx, rsi; Size
0x180029efb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029f00  mov     [rsp+58h+arg_8], rax
0x180029f05  test    rax, rax
0x180029f08  jz      short loc_180029F1D
0x180029f0a  lea     r8, aSoftwarePolici; "Software\\Policies\\Microsoft\\PeerDist"
0x180029f11  mov     rdx, rbx; void *
0x180029f14  mov     rcx, rax; this
0x180029f17  call    ??0CRegistryContextTransacted@@QEAA@PEAXPEBG@Z; CRegistryContextTransacted::CRegistryContextTransacted(void *,ushort const *)
0x180029f1c  nop
0x180029f1d  mov     rdx, rax
0x180029f20  lea     rcx, [rdi+18h]
0x180029f24  call    ?reset@?$auto_ptr@VTnoHashKey@@@std@@QEAAXPEAVTnoHashKey@@@Z; std::auto_ptr<TnoHashKey>::reset(TnoHashKey *)
0x180029f29  nop
0x180029f2a  mov     rax, rdi
0x180029f2d  mov     rbx, [rsp+58h+arg_10]
0x180029f32  mov     rsi, [rsp+58h+arg_18]
0x180029f37  add     rsp, 40h
0x180029f3b  pop     r15
0x180029f3d  pop     r14
0x180029f3f  pop     rdi
0x180029f40  retn
0x180029f41  call    cs:__imp_GetLastError
0x180029f47  nop
0x180029f48  mov     ebx, eax
0x180029f4a  lea     rax, WPP_GLOBAL_Control
0x180029f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180029f58  cmp     rcx, rax
0x180029f5b  jz      short loc_180029F84
0x180029f5d  test    dword ptr [rcx+6Ch], 200h
0x180029f64  jz      short loc_180029F84
0x180029f66  cmp     byte ptr [rcx+69h], 1
0x180029f6a  jb      short loc_180029F84
0x180029f6c  mov     edx, 0Ah
0x180029f71  mov     r9d, ebx
0x180029f74  lea     r8, WPP_36d5d5f09d763694b71bd6725b4e7cf3_Traceguids
0x180029f7b  mov     rcx, [rcx+60h]
0x180029f7f  call    WPP_SF_d
0x180029f84  test    ebx, ebx
0x180029f86  jle     short loc_180029F91
0x180029f88  movzx   ebx, bx
0x180029f8b  or      ebx, 80070000h
0x180029f91  mov     edx, ebx; int
0x180029f93  lea     rcx, aCtnocfgmgrtran; "CTnoCfgMgrTransaction::CTnoCfgMgrTransa"...
0x180029f9a  call    ?ThrowHelper@SystemError@@CAXPEBGJ@Z; SystemError::ThrowHelper(ushort const *,long)
```

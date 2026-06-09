# KERBEROS_INFO::GetReferencedKerberosInfo(void)

- ea: `0x180003ed4`
- end: `0x180003fe8`
- name: `?GetReferencedKerberosInfo@KERBEROS_INFO@@SAPEAV1@XZ`
- size: `276`
- prototype: `struct KERBEROS_INFO *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002084`

## callees

- `0x180001024`
- `0x180001064`
- `0x180001c34`
- `0x180003ed4`
- `0x1800043dc`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f37`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f51`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f6b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f37`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f51`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003f6b`

## pseudocode

```c
struct KERBEROS_INFO *KERBEROS_INFO::GetReferencedKerberosInfo(void)
{
  signed __int32 v0; // ebp
  KERBEROS_INFO *v1; // rbx
  unsigned __int16 *v2; // rax
  signed __int32 v4[18]; // [rsp+0h] [rbp-48h] BYREF

  v0 = _InterlockedCompareExchange(&KERBEROS_INFO::sm_State, 1, 0);
  if ( v0 == 2 )
  {
    v1 = KERBEROS_INFO::sm_pKerberosInfo;
    if ( KERBEROS_INFO::sm_pKerberosInfo )
      _InterlockedAdd((volatile signed __int32 *)KERBEROS_INFO::sm_pKerberosInfo, 1u);
    return v1;
  }
  v2 = (unsigned __int16 *)operator new(0x248u);
  v1 = (KERBEROS_INFO *)v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = 1;
    STRU::STRU((STRU *)(v2 + 4), v2 + 32, 0x40u);
    STRU::STRU((KERBEROS_INFO *)((char *)v1 + 192), (unsigned __int16 *)v1 + 124, 0x40u);
    STRU::STRU((KERBEROS_INFO *)((char *)v1 + 376), (unsigned __int16 *)v1 + 216, 0x40u);
    *((_QWORD *)v1 + 70) = 0;
    *((_QWORD *)v1 + 71) = 0;
    *((_QWORD *)v1 + 72) = 0;
    if ( (int)KERBEROS_INFO::InitializeInstance(v1) >= 0 )
      goto LABEL_9;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      KERBEROS_INFO::~KERBEROS_INFO(v1);
      operator delete(v1);
    }
  }
  v1 = 0;
LABEL_9:
  if ( !v0 )
  {
    if ( v1 )
      _InterlockedAdd((volatile signed __int32 *)v1, 1u);
    _InterlockedOr(v4, 0);
    KERBEROS_INFO::sm_pKerberosInfo = v1;
    _InterlockedExchange(&KERBEROS_INFO::sm_State, 2);
  }
  return v1;
}

```

## disassembly

```asm
0x180003ed4  push    rbx
0x180003ed6  push    rbp
0x180003ed7  push    rsi
0x180003ed8  push    r15
0x180003eda  sub     rsp, 28h
0x180003ede  xor     eax, eax
0x180003ee0  lea     r15d, [rax+1]
0x180003ee4  lock cmpxchg cs:?sm_State@KERBEROS_INFO@@0JA, r15d; long KERBEROS_INFO::sm_State
0x180003eed  lea     esi, [r15+1]
0x180003ef1  mov     ebp, eax
0x180003ef3  cmp     eax, esi
0x180003ef5  jnz     short loc_180003F10
0x180003ef7  mov     rbx, cs:?sm_pKerberosInfo@KERBEROS_INFO@@0PEAV1@EA; KERBEROS_INFO * KERBEROS_INFO::sm_pKerberosInfo
0x180003efe  test    rbx, rbx
0x180003f01  jz      loc_180003FDB
0x180003f07  lock add [rbx], r15d
0x180003f0b  jmp     loc_180003FDB
0x180003f10  mov     ecx, 248h; Size
0x180003f15  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f1a  mov     rbx, rax
0x180003f1d  test    rax, rax
0x180003f20  jz      loc_180003FBA
0x180003f26  lea     rdx, [rax+40h]
0x180003f2a  mov     [rax], r15
0x180003f2d  lea     rcx, [rax+8]
0x180003f31  mov     r8d, 40h ; '@'
0x180003f37  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003f3d  lea     rdx, [rbx+0F8h]
0x180003f44  mov     r8d, 40h ; '@'
0x180003f4a  lea     rcx, [rbx+0C0h]
0x180003f51  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003f57  lea     rdx, [rbx+1B0h]
0x180003f5e  mov     r8d, 40h ; '@'
0x180003f64  lea     rcx, [rbx+178h]
0x180003f6b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003f71  mov     rcx, rbx; this
0x180003f74  mov     qword ptr [rbx+230h], 0
0x180003f7f  mov     qword ptr [rbx+238h], 0
0x180003f8a  mov     qword ptr [rbx+240h], 0
0x180003f95  call    ?InitializeInstance@KERBEROS_INFO@@QEAAJXZ; KERBEROS_INFO::InitializeInstance(void)
0x180003f9a  test    eax, eax
0x180003f9c  jns     short loc_180003FBC
0x180003f9e  or      eax, 0FFFFFFFFh
0x180003fa1  lock xadd [rbx], eax
0x180003fa5  cmp     eax, r15d
0x180003fa8  jnz     short loc_180003FBA
0x180003faa  mov     rcx, rbx; this
0x180003fad  call    ??1KERBEROS_INFO@@QEAA@XZ; KERBEROS_INFO::~KERBEROS_INFO(void)
0x180003fb2  mov     rcx, rbx; Block
0x180003fb5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003fba  xor     ebx, ebx
0x180003fbc  test    ebp, ebp
0x180003fbe  jnz     short loc_180003FDB
0x180003fc0  test    rbx, rbx
0x180003fc3  jz      short loc_180003FC9
0x180003fc5  lock add [rbx], r15d
0x180003fc9  lock or [rsp+48h+var_48], 0
0x180003fce  mov     cs:?sm_pKerberosInfo@KERBEROS_INFO@@0PEAV1@EA, rbx; KERBEROS_INFO * KERBEROS_INFO::sm_pKerberosInfo
0x180003fd5  xchg    esi, cs:?sm_State@KERBEROS_INFO@@0JA; long KERBEROS_INFO::sm_State
0x180003fdb  mov     rax, rbx
0x180003fde  add     rsp, 28h
0x180003fe2  pop     r15
0x180003fe4  pop     rsi
0x180003fe5  pop     rbp
0x180003fe6  pop     rbx
0x180003fe7  retn
```

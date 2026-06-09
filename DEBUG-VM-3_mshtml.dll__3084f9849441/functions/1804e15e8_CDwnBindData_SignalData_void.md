# CDwnBindData::SignalData(void)

- ea: `0x1804e15e8`
- end: `0x1804e1924`
- name: `?SignalData@CDwnBindData@@AEAAXXZ`
- size: `828`
- prototype: `void __fastcall(CDwnBindData *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1804df8c4`
- `0x1804e7d30`
- `0x1804e95a0`
- `0x1804e9790`
- `0x180725980`

## callees

- `0x180496b0c`
- `0x1804e15e8`
- `0x1804e192c`
- `0x1804e44e0`
- `0x18062947c`
- `0x1810c2d60`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1804e182d`
- `msvcrt!memcpy_s` at `0x1804e182d`
- `KERNEL32!GetCurrentThreadId` at `0x1804e16cd`
- `KERNEL32!GetCurrentThreadId` at `0x1804e16cd`
- `KERNEL32!LeaveCriticalSection` at `0x1804e165f`
- `KERNEL32!LeaveCriticalSection` at `0x1804e165f`
- `KERNEL32!EnterCriticalSection` at `0x1804e1642`
- `KERNEL32!EnterCriticalSection` at `0x1804e1642`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e16fd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e1706`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e1710`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e171a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e17e3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e17ed`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e16fd`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e1706`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e1710`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e171a`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e17e3`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1804e17ed`

## pseudocode

```c
void __fastcall CDwnBindData::SignalData(CDwnBindData *this)
{
  __int16 v2; // bp
  __int64 v3; // rdi
  __int16 v4; // si
  bool v5; // zf
  DWORD CurrentThreadId; // eax
  __int128 v7; // xmm6
  __int128 v8; // xmm7
  char v9; // r15
  struct IE_GLOBAL_THREAD_STATE *v10; // rax
  int v11; // ebp
  const void *v12; // r8
  CDwnBindData *v13; // rcx
  _BYTE v14[8]; // [rsp+20h] [rbp-78h] BYREF
  __int64 Destination; // [rsp+28h] [rbp-70h] BYREF
  int v16; // [rsp+30h] [rbp-68h]

  if ( *((_BYTE *)this + 792) && *((_QWORD *)this + 50) )
    CDwnBindData::BufferData(this);
  v2 = 32;
  _InterlockedIncrement((volatile signed __int32 *)this + 5);
  while ( 1 )
  {
    v3 = 0;
    LOBYTE(v4) = 0;
    EnterCriticalSection(&g_csDwnBindSig);
    *((_WORD *)this + 218) |= v2;
    if ( *((_QWORD *)this + 56) )
    {
      v5 = ((unsigned __int16)v2 | *((_WORD *)this + 219)) == 0;
      *((_WORD *)this + 219) |= v2;
      if ( !v5 && !*((_DWORD *)this + 110) )
      {
        v4 = *((_WORD *)this + 219);
        *((_WORD *)this + 219) = 0;
        CurrentThreadId = GetCurrentThreadId();
        v3 = *((_QWORD *)this + 56);
        *((_DWORD *)this + 110) = CurrentThreadId;
        _InterlockedIncrement((volatile signed __int32 *)(v3 + 20));
      }
    }
    LeaveCriticalSection(&g_csDwnBindSig);
    if ( !v3 )
      break;
    if ( !*((_BYTE *)this + 792) && *((_QWORD *)this + 50) && (v4 & 0x20) != 0 )
      CDwnBindData::BufferData(this);
    v7 = *(_OWORD *)((char *)this + 1080);
    v8 = *(_OWORD *)GlobalThreadState();
    v9 = *((_BYTE *)GlobalThreadState() + 16);
    *(_OWORD *)GlobalThreadState() = v7;
    v10 = GlobalThreadState();
    v14[0] = 0;
    *((_BYTE *)v10 + 16) = 1;
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v3 + 24LL))(v3, v14);
    if ( !v14[0] )
    {
      if ( (v4 & 1) != 0 )
      {
        v12 = (const void *)(*(_QWORD *)(v3 + 40) + 424LL);
        Destination = 0;
        v16 = 0;
        memcpy_s(&Destination, 0xCu, v12, 0xCu);
        v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 40LL))(v3, &Destination);
        if ( v11 )
          goto LABEL_21;
      }
      if ( (v4 & 2) != 0
        && (v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v3 + 48LL))(
                    v3,
                    *(_QWORD *)(*(_QWORD *)(v3 + 40) + 512LL),
                    *(_QWORD *)(*(_QWORD *)(v3 + 40) + 528LL))) != 0
        || (v4 & 8) != 0
        && (CDwnBindData::AddToPrivacyList(*(CDwnBindData **)(v3 + 40)),
            (v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 56LL))(v3)) != 0)
        || (v4 & 0x10) != 0
        && (v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 64LL))(
                    v3,
                    *(_QWORD *)(*(_QWORD *)(v3 + 40) + 456LL))) != 0 )
      {
LABEL_21:
        if ( v11 >= 0 )
          goto LABEL_22;
        if ( !*(_DWORD *)(v3 + 92) )
        {
          v13 = *(CDwnBindData **)(v3 + 40);
          *(_DWORD *)(v3 + 92) = 1;
          CDwnBindData::Disconnect(v13);
          CDwnBindData::Terminate(*(CDwnBindData **)(v3 + 40), v11);
        }
        goto LABEL_23;
      }
      if ( (v4 & 0x20) != 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 72LL))(v3);
        goto LABEL_21;
      }
LABEL_22:
      if ( (v4 & 0x40) != 0 )
LABEL_23:
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 80LL))(
          v3,
          *(unsigned int *)(*(_QWORD *)(v3 + 40) + 756LL));
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 20), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v3)(v3, 1);
    *(_OWORD *)GlobalThreadState() = v8;
    v2 = 0;
    *((_BYTE *)GlobalThreadState() + 16) = v9;
    *((_DWORD *)this + 110) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 5, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(CDwnBindData *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x1804e15e8  push    rbx
0x1804e15ea  push    rbp
0x1804e15eb  push    rsi
0x1804e15ec  push    rdi
0x1804e15ed  push    r14
0x1804e15ef  push    r15
0x1804e15f1  sub     rsp, 68h
0x1804e15f5  movaps  [rsp+98h+var_48], xmm6
0x1804e15fa  movaps  [rsp+98h+var_58], xmm7
0x1804e15ff  mov     rax, cs:__security_cookie
0x1804e1606  xor     rax, rsp
0x1804e1609  mov     [rsp+98h+var_60], rax
0x1804e160e  cmp     byte ptr [rcx+318h], 0
0x1804e1615  mov     rbx, rcx
0x1804e1618  jz      short loc_1804E1629
0x1804e161a  cmp     qword ptr [rcx+190h], 0
0x1804e1622  jz      short loc_1804E1629
0x1804e1624  call    ?BufferData@CDwnBindData@@AEAAXXZ; CDwnBindData::BufferData(void)
0x1804e1629  mov     r14d, 20h ; ' '
0x1804e162f  movzx   ebp, r14w
0x1804e1633  lock inc dword ptr [rbx+14h]
0x1804e1637  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x1804e163e  xor     edi, edi
0x1804e1640  xor     esi, esi
0x1804e1642  call    cs:__imp_EnterCriticalSection
0x1804e1648  or      [rbx+1B4h], bp
0x1804e164f  cmp     [rbx+1C0h], rsi
0x1804e1656  jnz     short loc_1804E16AC
0x1804e1658  lea     rcx, ?g_csDwnBindSig@@3VCGlobalDwnCrit@@A; lpCriticalSection
0x1804e165f  call    cs:__imp_LeaveCriticalSection
0x1804e1665  test    rdi, rdi
0x1804e1668  jnz     short loc_1804E16E9
0x1804e166a  or      eax, 0FFFFFFFFh
0x1804e166d  lock xadd [rbx+14h], eax
0x1804e1672  cmp     eax, 1
0x1804e1675  jnz     short loc_1804E1688
0x1804e1677  mov     rax, [rbx]
0x1804e167a  lea     edx, [rdi+1]
0x1804e167d  mov     rcx, rbx
0x1804e1680  mov     rax, [rax]
0x1804e1683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e1688  mov     rcx, [rsp+98h+var_60]
0x1804e168d  xor     rcx, rsp; StackCookie
0x1804e1690  call    __security_check_cookie
0x1804e1695  movaps  xmm6, [rsp+98h+var_48]
0x1804e169a  movaps  xmm7, [rsp+98h+var_58]
0x1804e169f  add     rsp, 68h
0x1804e16a3  pop     r15
0x1804e16a5  pop     r14
0x1804e16a7  pop     rdi
0x1804e16a8  pop     rsi
0x1804e16a9  pop     rbp
0x1804e16aa  pop     rbx
0x1804e16ab  retn
0x1804e16ac  or      [rbx+1B6h], bp
0x1804e16b3  jz      short loc_1804E1658
0x1804e16b5  mov     eax, [rbx+1B8h]
0x1804e16bb  test    eax, eax
0x1804e16bd  jnz     short loc_1804E1658
0x1804e16bf  movzx   esi, word ptr [rbx+1B6h]
0x1804e16c6  mov     [rbx+1B6h], ax
0x1804e16cd  call    cs:__imp_GetCurrentThreadId
0x1804e16d3  mov     rdi, [rbx+1C0h]
0x1804e16da  mov     [rbx+1B8h], eax
0x1804e16e0  lock inc dword ptr [rdi+14h]
0x1804e16e4  jmp     loc_1804E1658
0x1804e16e9  cmp     byte ptr [rbx+318h], 0
0x1804e16f0  jz      loc_1804E1856
0x1804e16f6  movups  xmm6, xmmword ptr [rbx+438h]
0x1804e16fd  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e1703  movups  xmm7, xmmword ptr [rax]
0x1804e1706  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e170c  mov     r15b, [rax+10h]
0x1804e1710  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e1716  movdqu  xmmword ptr [rax], xmm6
0x1804e171a  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e1720  lea     rdx, [rsp+98h+var_78]
0x1804e1725  mov     [rsp+98h+var_78], 0
0x1804e172a  mov     rcx, rdi
0x1804e172d  mov     byte ptr [rax+10h], 1
0x1804e1731  mov     rax, [rdi]
0x1804e1734  mov     rax, [rax+18h]
0x1804e1738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e173d  cmp     [rsp+98h+var_78], 0
0x1804e1742  jnz     short loc_1804E17C3
0x1804e1744  movzx   r14d, si
0x1804e1748  test    sil, 1
0x1804e174c  jnz     loc_1804E1808
0x1804e1752  test    sil, 2
0x1804e1756  jnz     loc_1804E18CA
0x1804e175c  test    sil, 8
0x1804e1760  jnz     loc_1804E187A
0x1804e1766  test    sil, 10h
0x1804e176a  jnz     loc_1804E18A1
0x1804e1770  test    sil, 20h
0x1804e1774  jz      short loc_1804E178F
0x1804e1776  mov     rax, [rdi]
0x1804e1779  mov     rcx, rdi
0x1804e177c  mov     rax, [rax+48h]
0x1804e1780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e1785  mov     ebp, eax
0x1804e1787  test    ebp, ebp
0x1804e1789  js      loc_1804E18FA
0x1804e178f  test    r14b, 40h
0x1804e1793  jz      short loc_1804E17AE
0x1804e1795  mov     rax, [rdi]
0x1804e1798  mov     rcx, rdi
0x1804e179b  mov     rdx, [rdi+28h]
0x1804e179f  mov     rax, [rax+50h]
0x1804e17a3  mov     edx, [rdx+2F4h]
0x1804e17a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e17ae  mov     rax, [rdi]
0x1804e17b1  mov     rcx, rdi
0x1804e17b4  mov     rax, [rax+20h]
0x1804e17b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e17bd  mov     r14d, 20h ; ' '
0x1804e17c3  or      eax, 0FFFFFFFFh
0x1804e17c6  lock xadd [rdi+14h], eax
0x1804e17cb  cmp     eax, 1
0x1804e17ce  jnz     short loc_1804E17E3
0x1804e17d0  mov     rax, [rdi]
0x1804e17d3  mov     edx, 1
0x1804e17d8  mov     rcx, rdi
0x1804e17db  mov     rax, [rax]
0x1804e17de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e17e3  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e17e9  movdqu  xmmword ptr [rax], xmm7
0x1804e17ed  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1804e17f3  xor     ebp, ebp
0x1804e17f5  mov     [rax+10h], r15b
0x1804e17f9  mov     dword ptr [rbx+1B8h], 0
0x1804e1803  jmp     loc_1804E1637
0x1804e1808  mov     r8, [rdi+28h]
0x1804e180c  lea     rcx, [rsp+98h+Destination]; Destination
0x1804e1811  xor     eax, eax
0x1804e1813  add     r8, 1A8h; Source
0x1804e181a  mov     [rsp+98h+Destination], rax
0x1804e181f  mov     [rsp+98h+var_68], eax
0x1804e1823  mov     eax, 0Ch
0x1804e1828  mov     r9d, eax; SourceSize
0x1804e182b  mov     edx, eax; DestinationSize
0x1804e182d  call    cs:__imp_memcpy_s
0x1804e1833  mov     rax, [rdi]
0x1804e1836  lea     rdx, [rsp+98h+Destination]
0x1804e183b  mov     rcx, rdi
0x1804e183e  mov     rax, [rax+28h]
0x1804e1842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e1847  mov     ebp, eax
0x1804e1849  test    eax, eax
0x1804e184b  jz      loc_1804E1752
0x1804e1851  jmp     loc_1804E1787
0x1804e1856  cmp     qword ptr [rbx+190h], 0
0x1804e185e  jz      loc_1804E16F6
0x1804e1864  test    r14b, sil
0x1804e1867  jz      loc_1804E16F6
0x1804e186d  mov     rcx, rbx; this
0x1804e1870  call    ?BufferData@CDwnBindData@@AEAAXXZ; CDwnBindData::BufferData(void)
0x1804e1875  jmp     loc_1804E16F6
0x1804e187a  mov     rcx, [rdi+28h]; this
0x1804e187e  call    ?AddToPrivacyList@CDwnBindData@@QEAAXXZ; CDwnBindData::AddToPrivacyList(void)
0x1804e1883  mov     rax, [rdi]
0x1804e1886  mov     rcx, rdi
0x1804e1889  mov     rax, [rax+38h]
0x1804e188d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e1892  mov     ebp, eax
0x1804e1894  test    eax, eax
0x1804e1896  jz      loc_1804E1766
0x1804e189c  jmp     loc_1804E1787
0x1804e18a1  mov     rax, [rdi]
0x1804e18a4  mov     rcx, rdi
0x1804e18a7  mov     rdx, [rdi+28h]
0x1804e18ab  mov     rax, [rax+40h]
0x1804e18af  mov     rdx, [rdx+1C8h]
0x1804e18b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e18bb  mov     ebp, eax
0x1804e18bd  test    eax, eax
0x1804e18bf  jz      loc_1804E1770
0x1804e18c5  jmp     loc_1804E1787
0x1804e18ca  mov     rdx, [rdi+28h]
0x1804e18ce  mov     rcx, rdi
0x1804e18d1  mov     rax, [rdi]
0x1804e18d4  mov     r8, [rdx+210h]
0x1804e18db  mov     rdx, [rdx+200h]
0x1804e18e2  mov     rax, [rax+30h]
0x1804e18e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804e18eb  mov     ebp, eax
0x1804e18ed  test    eax, eax
0x1804e18ef  jnz     loc_1804E1787
0x1804e18f5  jmp     loc_1804E175C
0x1804e18fa  cmp     dword ptr [rdi+5Ch], 0
0x1804e18fe  jnz     loc_1804E1795
0x1804e1904  mov     rcx, [rdi+28h]; this
0x1804e1908  mov     dword ptr [rdi+5Ch], 1
0x1804e190f  call    ?Disconnect@CDwnBindData@@QEAAXXZ; CDwnBindData::Disconnect(void)
0x1804e1914  mov     rcx, [rdi+28h]; this
0x1804e1918  mov     edx, ebp; int
0x1804e191a  call    ?Terminate@CDwnBindData@@QEAAXJ@Z; CDwnBindData::Terminate(long)
0x1804e191f  jmp     loc_1804E1795
```

# Broker::ApplicationStateTable::State::OnEventCreation(ulong,ulong)

- ea: `0x1800119f4`
- end: `0x180011ac8`
- name: `?OnEventCreation@State@ApplicationStateTable@Broker@@QEAAXKK@Z`
- size: `212`
- prototype: `void(Broker::ApplicationStateTable::State *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800192fc`

## callees

- `0x18000eb40`
- `0x18000ed50`
- `0x1800119f4`
- `0x1800165da`
- `0x18001a170`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::ApplicationStateTable::State::OnEventCreation(
        struct _RTL_SRWLOCK *this,
        unsigned int a2,
        int a3)
{
  __int64 v4; // rsi
  _DWORD *Ptr; // rdx
  __int64 v7; // r8
  unsigned int v8; // ecx
  const wchar_t *v9; // rax
  char v10[4]; // [rsp+38h] [rbp-60h]
  _BYTE v11[16]; // [rsp+40h] [rbp-58h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-48h] BYREF
  __int128 v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+68h] [rbp-30h]

  v4 = a2;
  if ( *((_DWORD *)this[11].Ptr + a2) != -1 )
  {
    Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v11, this + 18, 1);
    Ptr = this[14].Ptr;
    v7 = (unsigned int)Ptr[v4];
    v8 = v7 + a3;
    if ( (int)v7 + a3 < (unsigned int)v7 || v8 > *((_DWORD *)this[11].Ptr + v4) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v9 = (const wchar_t *)&this[7];
        if ( this[10].Ptr > (PVOID)7 )
          v9 = *(const wchar_t **)v9;
        *(_DWORD *)v10 = *((_DWORD *)this[11].Ptr + v4);
        WPP_SF__sid_Sddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(unsigned int *)v10,
          v7,
          (char *)this->Ptr,
          v9,
          v4,
          v7,
          *(_DWORD *)v10);
      }
      v13 = 0;
      v14 = 2;
      pExceptionObject = &Broker::ApplicationLimitsExceeded::`vftable';
      throw (Broker::ApplicationLimitsExceeded *)&pExceptionObject;
    }
    Ptr[v4] = v8;
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v11);
  }
}

```

## disassembly

```asm
0x1800119f4  push    rbx
0x1800119f6  push    rbp
0x1800119f7  push    rsi
0x1800119f8  push    rdi
0x1800119f9  sub     rsp, 78h
0x1800119fd  mov     ebp, r8d
0x180011a00  mov     esi, edx
0x180011a02  mov     rbx, rcx
0x180011a05  mov     rax, [rcx+58h]
0x180011a09  cmp     dword ptr [rax+rsi*4], 0FFFFFFFFh
0x180011a0d  jz      short loc_180011A4B
0x180011a0f  lea     rdx, [rcx+90h]; struct _RTL_SRWLOCK *
0x180011a16  mov     r8b, 1; bool
0x180011a19  lea     rcx, [rsp+98h+var_58]; this
0x180011a1e  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x180011a23  nop
0x180011a24  mov     rdx, [rbx+70h]
0x180011a28  mov     r8d, [rdx+rsi*4]
0x180011a2c  lea     ecx, [r8+rbp]
0x180011a30  cmp     ecx, r8d
0x180011a33  jb      short loc_180011A54
0x180011a35  mov     rax, [rbx+58h]
0x180011a39  cmp     ecx, [rax+rsi*4]
0x180011a3c  ja      short loc_180011A54
0x180011a3e  mov     [rdx+rsi*4], ecx
0x180011a41  lea     rcx, [rsp+98h+var_58]; this
0x180011a46  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180011a4b  add     rsp, 78h
0x180011a4f  pop     rdi
0x180011a50  pop     rsi
0x180011a51  pop     rbp
0x180011a52  pop     rbx
0x180011a53  retn
0x180011a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a5b  test    byte ptr [rcx+1Ch], 2
0x180011a5f  jz      short loc_180011A9A
0x180011a61  cmp     byte ptr [rcx+19h], 3
0x180011a65  jb      short loc_180011A9A
0x180011a67  mov     rax, [rbx+58h]
0x180011a6b  mov     edx, [rax+rsi*4]
0x180011a6e  lea     rax, [rbx+38h]
0x180011a72  cmp     qword ptr [rax+18h], 7
0x180011a77  jbe     short loc_180011A7C
0x180011a79  mov     rax, [rax]
0x180011a7c  mov     dword ptr [rsp+98h+var_60], edx; char
0x180011a80  mov     dword ptr [rsp+98h+var_68], r8d; char
0x180011a85  mov     dword ptr [rsp+98h+var_70], esi; char
0x180011a89  mov     [rsp+98h+var_78], rax; __int64
0x180011a8e  mov     r9, [rbx]
0x180011a91  mov     rcx, [rcx+10h]; LoggerHandle
0x180011a95  call    WPP_SF__sid_Sddd
0x180011a9a  xorps   xmm0, xmm0
0x180011a9d  movups  [rsp+98h+var_40], xmm0
0x180011aa2  mov     [rsp+98h+var_30], 2
0x180011aaa  lea     rax, ??_7ApplicationLimitsExceeded@Broker@@6B@; const Broker::ApplicationLimitsExceeded::`vftable'
0x180011ab1  mov     [rsp+98h+pExceptionObject], rax
0x180011ab6  lea     rdx, _TI3?AUApplicationLimitsExceeded@Broker@@; pThrowInfo
0x180011abd  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180011ac2  call    _CxxThrowException_0
```

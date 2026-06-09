# WinSAT::MPOperation::StartWorkloads(WinSAT::OpStatus &)

- ea: `0x1400123b4`
- end: `0x1400124d2`
- name: `?StartWorkloads@MPOperation@WinSAT@@AEAA_NAEAVOpStatus@2@@Z`
- size: `286`
- prototype: `bool __fastcall(WinSAT::MPOperation *__hidden this, struct WinSAT::OpStatus *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400120e0`

## callees

- `0x14000fefc`
- `0x140011f58`
- `0x1400123b4`
- `0x140016588`
- `0x14004fe00`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140012431`
- `KERNEL32!WaitForSingleObject` at `0x140012431`
- `msvcrt!_beginthreadex` at `0x1400123f6`
- `msvcrt!_beginthreadex` at `0x1400123f6`

## pseudocode

```c
char __fastcall WinSAT::MPOperation::StartWorkloads(WinSAT::MPOperation *this, struct WinSAT::OpStatus *a2)
{
  uintptr_t v4; // rax
  unsigned __int16 v5; // r9
  int v6; // ecx
  __int64 v7; // r15
  char v8; // si
  const unsigned __int16 *v9; // rax
  __int64 v10; // rbx
  unsigned int ThrdAddr; // [rsp+70h] [rbp+18h] BYREF

  ThrdAddr = 0;
  v4 = _beginthreadex(0, 0, WinSAT::MPOperation::CompletionThreadCallback, this, 0, &ThrdAddr);
  v6 = *((_DWORD *)this + 2075);
  if ( v4 )
  {
    *((_QWORD *)this + 1048) = v4;
    v10 = 0;
    if ( v6 )
    {
      do
      {
        WinSAT::MPWorkload::ResumeThread(*((WinSAT::MPWorkload **)this + v10 + 13));
        v10 = (unsigned int)(v10 + 1);
      }
      while ( (unsigned int)v10 < *((_DWORD *)this + 2075) );
    }
    *((_DWORD *)this + 14) = 4;
    *(_DWORD *)a2 = 4;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((char *)a2 + 8);
    *((_BYTE *)a2 + 16) = 0;
    return 0;
  }
  else
  {
    v7 = 0;
    v8 = 1;
    if ( v6 )
    {
      do
      {
        _InterlockedAdd((volatile signed __int32 *)this + 2080, 1u);
        WinSAT::MPWorkload::ResumeThread(*((WinSAT::MPWorkload **)this + v7 + 13));
        WaitForSingleObject(*(HANDLE *)(*((_QWORD *)this + v7 + 13) + 816LL), 0xFFFFFFFF);
        _InterlockedDecrement((volatile signed __int32 *)this + 2080);
        v7 = (unsigned int)(v7 + 1);
      }
      while ( (unsigned int)v7 < *((_DWORD *)this + 2075) );
    }
    *((_DWORD *)this + 14) = 5;
    try
    {
      v9 = mlib::MUIStr_((mlib *)"base\\winsat\\exe\\WinSATOp.h", (const char *)0x683, 10125, v5);
      WinSAT::OpStatus::SetResult(a2, *((unsigned int *)this + 14), v9, 0);
    }
    catch ( std::bad_alloc )
    {
      *(_DWORD *)a2 = *((_DWORD *)this + 14);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear((char *)a2 + 8);
      *((_BYTE *)a2 + 16) = 0;
      return 1;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1400123b4  mov     rax, rsp
0x1400123b7  mov     [rax+10h], rdx
0x1400123bb  mov     [rax+8], rcx
0x1400123bf  push    rbx
0x1400123c0  push    rsi
0x1400123c1  push    rdi
0x1400123c2  push    r14
0x1400123c4  push    r15
0x1400123c6  sub     rsp, 30h
0x1400123ca  mov     r14, rdx
0x1400123cd  mov     rdi, rcx
0x1400123d0  mov     dword ptr [rax+18h], 0
0x1400123d7  lea     rax, [rax+18h]
0x1400123db  mov     [rsp+58h+ThrdAddr], rax; ThrdAddr
0x1400123e0  mov     [rsp+58h+InitFlag], 0; InitFlag
0x1400123e8  mov     r9, rcx; ArgList
0x1400123eb  lea     r8, ?CompletionThreadCallback@MPOperation@WinSAT@@CAIPEAX@Z; StartAddress
0x1400123f2  xor     edx, edx; StackSize
0x1400123f4  xor     ecx, ecx; Security
0x1400123f6  call    cs:__imp__beginthreadex
0x1400123fc  mov     ecx, [rdi+206Ch]
0x140012402  test    rax, rax
0x140012405  jnz     short loc_140012483
0x140012407  xor     r15d, r15d
0x14001240a  lea     esi, [rax+1]
0x14001240d  test    ecx, ecx
0x14001240f  jz      short loc_14001244A
0x140012411  lock add [rdi+2080h], esi
0x140012418  mov     rcx, [rdi+r15*8+68h]; this
0x14001241d  call    ?ResumeThread@MPWorkload@WinSAT@@QEBA_NXZ; WinSAT::MPWorkload::ResumeThread(void)
0x140012422  mov     rcx, [rdi+r15*8+68h]
0x140012427  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001242a  mov     rcx, [rcx+330h]; hHandle
0x140012431  call    cs:__imp_WaitForSingleObject
0x140012437  lock dec dword ptr [rdi+2080h]
0x14001243e  add     r15d, esi
0x140012441  cmp     r15d, [rdi+206Ch]
0x140012448  jb      short loc_140012411
0x14001244a  mov     dword ptr [rdi+38h], 5
0x140012451  mov     edx, 683h; char *
0x140012456  mov     r8d, 278Dh; int
0x14001245c  lea     rcx, aBaseWinsatExeW_0; "base\\winsat\\exe\\WinSATOp.h"
0x140012463  call    ?MUIStr_@mlib@@YAPEBGPEBDHG@Z; mlib::MUIStr_(char const *,int,ushort)
0x140012468  xor     r9d, r9d
0x14001246b  mov     r8, rax
0x14001246e  mov     edx, [rdi+38h]
0x140012471  mov     rcx, r14
0x140012474  call    ?SetResult@OpStatus@WinSAT@@QEAAXW4OpStatusCode@2@PEBGK@Z; WinSAT::OpStatus::SetResult(WinSAT::OpStatusCode,ushort const *,ulong)
0x140012479  nop
0x14001247a  jmp     short loc_1400124C3
0x14001247c  mov     esi, 1
0x140012481  jmp     short loc_1400124C3
0x140012483  mov     [rdi+20C0h], rax
0x14001248a  xor     ebx, ebx
0x14001248c  test    ecx, ecx
0x14001248e  jz      short loc_1400124A7
0x140012490  lea     esi, [rbx+1]
0x140012493  mov     rcx, [rdi+rbx*8+68h]; this
0x140012498  call    ?ResumeThread@MPWorkload@WinSAT@@QEBA_NXZ; WinSAT::MPWorkload::ResumeThread(void)
0x14001249d  add     ebx, esi
0x14001249f  cmp     ebx, [rdi+206Ch]
0x1400124a5  jb      short loc_140012493
0x1400124a7  mov     eax, 4
0x1400124ac  mov     [rdi+38h], eax
0x1400124af  mov     [r14], eax
0x1400124b2  lea     rcx, [r14+8]
0x1400124b6  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x1400124bb  mov     byte ptr [r14+10h], 0
0x1400124c0  xor     sil, sil
0x1400124c3  mov     al, sil
0x1400124c6  add     rsp, 30h
0x1400124ca  pop     r15
0x1400124cc  pop     r14
0x1400124ce  pop     rdi
0x1400124cf  pop     rsi
0x1400124d0  pop     rbx
0x1400124d1  retn
```

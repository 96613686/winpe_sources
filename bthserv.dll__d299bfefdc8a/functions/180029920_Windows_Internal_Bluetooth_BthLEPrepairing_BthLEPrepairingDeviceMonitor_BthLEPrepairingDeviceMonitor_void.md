# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(void)

- ea: `0x180029920`
- end: `0x180029aad`
- name: `??1BthLEPrepairingDeviceMonitor@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ`
- size: `397`
- prototype: `void __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x1800297b0`
- `0x180029864`
- `0x180029ab4`
- `0x18002a610`

## callees

- `0x180001b60`
- `0x1800296fc`
- `0x180029920`
- `0x18002c640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029a6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029a6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor::~BthLEPrepairingDeviceMonitor(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDeviceMonitor *this)
{
  void **v1; // r14
  __int64 *v3; // rbx
  _QWORD *v4; // rdi
  __int64 **v5; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *v8; // rbx
  void *v9; // rcx
  __int64 v10; // rcx
  void *v11; // rbx
  _QWORD **v12; // rcx
  _QWORD *v13; // rdx
  _QWORD *v14; // rbx
  void *v15; // rcx
  _QWORD **v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rbx

  v1 = (void **)((char *)this + 56);
  v3 = (__int64 *)**((_QWORD **)this + 7);
  while ( 1 )
  {
    v4 = *v1;
    if ( v3 == *v1 )
      break;
    operator delete((void *)v3[5], (const struct std::nothrow_t *)1);
    v3[5] = 0;
    v5 = (__int64 **)v3[2];
    if ( *((_BYTE *)v5 + 25) )
    {
      for ( i = (__int64 *)v3[1]; !*((_BYTE *)i + 25) && v3 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v3 = i;
      v3 = i;
    }
    else
    {
      v3 = (__int64 *)v3[2];
      for ( j = *v5; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v3 = j;
    }
  }
  v8 = (_QWORD *)v4[1];
  while ( !*((_BYTE *)v8 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(
      v1,
      v1,
      v8[2]);
    v9 = v8;
    v8 = (_QWORD *)*v8;
    operator delete(v9, (const struct std::nothrow_t *)0x30);
  }
  v4[1] = v4;
  *v4 = v4;
  v4[2] = v4;
  v1[1] = 0;
  while ( *((_QWORD *)this + 1) )
  {
    v10 = *(_QWORD *)(*(_QWORD *)this + 8LL);
    v11 = *(void **)(v10 + 16);
    if ( v11 )
    {
      Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(*(PTP_TIMER **)(v10 + 16));
      operator delete(v11, (const struct std::nothrow_t *)0x810);
    }
    v12 = *(_QWORD ***)(*(_QWORD *)this + 8LL);
    v13 = *v12;
    --*((_QWORD *)this + 1);
    *v12[1] = v13;
    v13[1] = v12[1];
    operator delete(v12, (const struct std::nothrow_t *)0x18);
  }
  v14 = (_QWORD *)*((_QWORD *)*v1 + 1);
  while ( !*((_BYTE *)v14 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(
      v1,
      v1,
      v14[2]);
    v15 = v14;
    v14 = (_QWORD *)*v14;
    operator delete(v15, (const struct std::nothrow_t *)0x30);
  }
  operator delete(*v1, (const struct std::nothrow_t *)0x30);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v16 = *(_QWORD ***)this;
  **(_QWORD **)(*(_QWORD *)this + 8LL) = 0;
  v17 = *v16;
  if ( v17 )
  {
    do
    {
      v18 = (_QWORD *)*v17;
      operator delete(v17, (const struct std::nothrow_t *)0x18);
      v17 = v18;
    }
    while ( v18 );
  }
  operator delete(*(void **)this, (const struct std::nothrow_t *)0x18);
}

```

## disassembly

```asm
0x180029920  push    rbx
0x180029922  push    rbp
0x180029923  push    rsi
0x180029924  push    rdi
0x180029925  push    r14
0x180029927  push    r15
0x180029929  sub     rsp, 28h
0x18002992d  lea     r14, [rcx+38h]
0x180029931  mov     rsi, rcx
0x180029934  mov     rbx, [r14]
0x180029937  xor     ebp, ebp
0x180029939  mov     rbx, [rbx]
0x18002993c  mov     rdi, [r14]
0x18002993f  cmp     rbx, rdi
0x180029942  jz      short loc_18002999B
0x180029944  mov     rcx, [rbx+28h]; void *
0x180029948  mov     edx, 1; struct std::nothrow_t *
0x18002994d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029952  mov     [rbx+28h], rbp
0x180029956  mov     rcx, [rbx+10h]
0x18002995a  cmp     [rcx+19h], bpl
0x18002995e  jz      short loc_18002997E
0x180029960  mov     rax, [rbx+8]
0x180029964  jmp     short loc_180029973
0x180029966  cmp     rbx, [rax+10h]
0x18002996a  jnz     short loc_180029979
0x18002996c  mov     rbx, rax
0x18002996f  mov     rax, [rax+8]
0x180029973  cmp     [rax+19h], bpl
0x180029977  jz      short loc_180029966
0x180029979  mov     rbx, rax
0x18002997c  jmp     short loc_18002993C
0x18002997e  mov     rbx, rcx
0x180029981  mov     rcx, [rcx]
0x180029984  cmp     [rcx+19h], bpl
0x180029988  jnz     short loc_18002993C
0x18002998a  mov     rax, [rcx]
0x18002998d  mov     rbx, rcx
0x180029990  mov     rcx, rax
0x180029993  cmp     [rax+19h], bpl
0x180029997  jz      short loc_18002998A
0x180029999  jmp     short loc_18002993C
0x18002999b  mov     rbx, [rdi+8]
0x18002999f  mov     r15d, 30h ; '0'
0x1800299a5  jmp     short loc_1800299C4
0x1800299a7  mov     r8, [rbx+10h]
0x1800299ab  mov     rdx, r14
0x1800299ae  mov     rcx, r14
0x1800299b1  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAD@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *> *)
0x1800299b6  mov     rcx, rbx; void *
0x1800299b9  mov     rdx, r15; struct std::nothrow_t *
0x1800299bc  mov     rbx, [rbx]
0x1800299bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800299c4  cmp     [rbx+19h], bpl
0x1800299c8  jz      short loc_1800299A7
0x1800299ca  mov     [rdi+8], rdi
0x1800299ce  mov     [rdi], rdi
0x1800299d1  mov     [rdi+10h], rdi
0x1800299d5  mov     edi, 18h
0x1800299da  mov     [r14+8], rbp
0x1800299de  cmp     [rsi+8], rbp
0x1800299e2  jz      short loc_180029A30
0x1800299e4  mov     rax, [rsi]
0x1800299e7  mov     rcx, [rax+8]
0x1800299eb  mov     rbx, [rcx+10h]
0x1800299ef  test    rbx, rbx
0x1800299f2  jz      short loc_180029A09
0x1800299f4  mov     rcx, rbx; this
0x1800299f7  call    ??1BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAA@XZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::~BthLEPrepairingDevice(void)
0x1800299fc  mov     edx, 810h; struct std::nothrow_t *
0x180029a01  mov     rcx, rbx; void *
0x180029a04  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a09  mov     rax, [rsi]
0x180029a0c  mov     rcx, [rax+8]; void *
0x180029a10  mov     rdx, [rcx]
0x180029a13  dec     qword ptr [rsi+8]
0x180029a17  mov     rax, [rcx+8]
0x180029a1b  mov     [rax], rdx
0x180029a1e  mov     rax, [rcx+8]
0x180029a22  mov     [rdx+8], rax
0x180029a26  mov     rdx, rdi; struct std::nothrow_t *
0x180029a29  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a2e  jmp     short loc_1800299DE
0x180029a30  mov     rax, [r14]
0x180029a33  mov     rbx, [rax+8]
0x180029a37  jmp     short loc_180029A56
0x180029a39  mov     r8, [rbx+10h]
0x180029a3d  mov     rdx, r14
0x180029a40  mov     rcx, r14
0x180029a43  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KPEAD@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KPEAD@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,char *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,char *>,void *> *)
0x180029a48  mov     rcx, rbx; void *
0x180029a4b  mov     rdx, r15; struct std::nothrow_t *
0x180029a4e  mov     rbx, [rbx]
0x180029a51  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a56  cmp     [rbx+19h], bpl
0x180029a5a  jz      short loc_180029A39
0x180029a5c  mov     rcx, [r14]; void *
0x180029a5f  mov     rdx, r15; struct std::nothrow_t *
0x180029a62  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a67  lea     rcx, [rsi+10h]; lpCriticalSection
0x180029a6b  call    cs:__imp_DeleteCriticalSection
0x180029a71  mov     rcx, [rsi]
0x180029a74  mov     rax, [rcx+8]
0x180029a78  mov     [rax], rbp
0x180029a7b  mov     rcx, [rcx]; void *
0x180029a7e  test    rcx, rcx
0x180029a81  jz      short loc_180029A96
0x180029a83  mov     rbx, [rcx]
0x180029a86  mov     rdx, rdi; struct std::nothrow_t *
0x180029a89  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a8e  mov     rcx, rbx
0x180029a91  test    rbx, rbx
0x180029a94  jnz     short loc_180029A83
0x180029a96  mov     rcx, [rsi]; void *
0x180029a99  mov     rdx, rdi; struct std::nothrow_t *
0x180029a9c  add     rsp, 28h
0x180029aa0  pop     r15
0x180029aa2  pop     r14
0x180029aa4  pop     rdi
0x180029aa5  pop     rsi
0x180029aa6  pop     rbp
0x180029aa7  pop     rbx
0x180029aa8  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```

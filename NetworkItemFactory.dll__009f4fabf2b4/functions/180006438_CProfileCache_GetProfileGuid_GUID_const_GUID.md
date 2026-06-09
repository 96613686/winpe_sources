# CProfileCache::GetProfileGuid(_GUID const &,_GUID *)

- ea: `0x180006438`
- end: `0x1800064ee`
- name: `?GetProfileGuid@CProfileCache@@QEAAJAEBU_GUID@@PEAU2@@Z`
- size: `182`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this, const struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003d28`

## callees

- `0x180006438`
- `0x1800076c8`

## pseudocode

```c
__int64 __fastcall CProfileCache::GetProfileGuid(CProfileCache *this, const struct _GUID *a2, struct _GUID *a3)
{
  volatile signed __int32 *v5; // rcx
  signed __int32 v7; // r10d
  unsigned int v8; // r8d
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  struct _GUID v11; // xmm0
  signed __int32 v12; // edx

  v5 = (volatile signed __int32 *)((char *)this + 48);
  if ( (*v5 & 0xFFFF8000) != 0 || (v7 = *v5, v7 != _InterlockedCompareExchange(v5, v7 + 1, v7)) )
    CReaderWriterLock3::_LockSpin(v5, 2);
  v8 = 0;
  v9 = 0;
  if ( *((_DWORD *)this + 4) )
  {
    while ( 1 )
    {
      v10 = (_QWORD *)(*((_QWORD *)this + 4) + 16LL * (unsigned int)v9);
      if ( *(_QWORD *)&a2->Data1 == *v10 && *(_QWORD *)a2->Data4 == v10[1] )
        break;
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= *((_DWORD *)this + 4) )
      {
        v11 = *(struct _GUID *)*((_QWORD *)this + 5);
        goto LABEL_10;
      }
    }
    v11 = *(struct _GUID *)(*((_QWORD *)this + 5) + 16 * v9);
LABEL_10:
    *a3 = v11;
  }
  else
  {
    v8 = -2147024809;
  }
  do
    v12 = *((_DWORD *)this + 12);
  while ( v12 != _InterlockedCompareExchange((volatile signed __int32 *)this + 12, v12 - 1, v12) );
  return v8;
}

```

## disassembly

```asm
0x180006438  mov     [rsp+arg_0], rbx
0x18000643d  mov     [rsp+arg_8], rsi
0x180006442  push    rdi
0x180006443  sub     rsp, 20h
0x180006447  mov     rbx, rcx
0x18000644a  mov     rdi, r8
0x18000644d  add     rcx, 30h ; '0'
0x180006451  mov     rsi, rdx
0x180006454  mov     r10d, [rcx]
0x180006457  test    r10d, 0FFFF8000h
0x18000645e  jnz     short loc_180006471
0x180006460  lea     r9d, [r10+1]
0x180006464  mov     eax, r10d
0x180006467  lock cmpxchg [rcx], r9d
0x18000646c  cmp     r10d, eax
0x18000646f  jz      short loc_18000647B
0x180006471  mov     edx, 2
0x180006476  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x18000647b  xor     r8d, r8d
0x18000647e  mov     ecx, r8d
0x180006481  cmp     [rbx+10h], r8d
0x180006485  jbe     short loc_1800064C4
0x180006487  mov     rax, [rsi]
0x18000648a  mov     edx, ecx
0x18000648c  shl     rdx, 4
0x180006490  add     rdx, [rbx+20h]
0x180006494  cmp     rax, [rdx]
0x180006497  jnz     short loc_1800064A3
0x180006499  mov     rax, [rsi+8]
0x18000649d  cmp     rax, [rdx+8]
0x1800064a1  jz      short loc_1800064B3
0x1800064a3  inc     ecx
0x1800064a5  cmp     ecx, [rbx+10h]
0x1800064a8  jb      short loc_180006487
0x1800064aa  mov     rax, [rbx+28h]
0x1800064ae  movups  xmm0, xmmword ptr [rax]
0x1800064b1  jmp     short loc_1800064BE
0x1800064b3  mov     rax, [rbx+28h]
0x1800064b7  add     rcx, rcx
0x1800064ba  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800064be  movdqu  xmmword ptr [rdi], xmm0
0x1800064c2  jmp     short loc_1800064CA
0x1800064c4  mov     r8d, 80070057h
0x1800064ca  mov     edx, [rbx+30h]
0x1800064cd  mov     eax, edx
0x1800064cf  lea     ecx, [rdx-1]
0x1800064d2  lock cmpxchg [rbx+30h], ecx
0x1800064d7  cmp     edx, eax
0x1800064d9  jnz     short loc_1800064CA
0x1800064db  mov     rbx, [rsp+28h+arg_0]
0x1800064e0  mov     eax, r8d
0x1800064e3  mov     rsi, [rsp+28h+arg_8]
0x1800064e8  add     rsp, 20h
0x1800064ec  pop     rdi
0x1800064ed  retn
```

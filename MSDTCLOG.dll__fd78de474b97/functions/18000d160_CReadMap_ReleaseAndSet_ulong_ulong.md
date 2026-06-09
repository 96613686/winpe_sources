# CReadMap::ReleaseAndSet(ulong,ulong)

- ea: `0x18000d160`
- end: `0x18000d2e7`
- name: `?ReleaseAndSet@CReadMap@@QEAAHKK@Z`
- size: `391`
- prototype: `__int64 __fastcall(CReadMap *__hidden this, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180002bf0`
- `0x180002ea0`
- `0x180007d7c`
- `0x18000cdd8`
- `0x180012d89`
- `0x180012e0c`
- `0x180012e8f`
- `0x180012f2e`
- `0x180012fc0`
- `0x18001300d`
- `0x1800139f5`
- `0x180013a73`

## callees

- `0x180005b64`
- `0x18000c6b8`
- `0x18000d160`
- `0x18000d2f0`
- `0x18001266c`

## pseudocode

```c
__int64 __fastcall CReadMap::ReleaseAndSet(CReadMap *this, __int64 a2, unsigned int a3)
{
  unsigned int v3; // ebp
  unsigned int i; // esi
  unsigned int v7; // ecx
  __int128 v8; // xmm1
  int v9; // eax
  LPCVOID *v10; // rdx
  CLogStorage *v11; // rcx
  struct _RECORDPAGE *FirstPage; // rax
  __int64 v14; // rdx
  int v15; // r8d
  __int64 v16; // rax
  ulong pExceptionObject; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  for ( i = a2; v3 < *((_DWORD *)this + 2); ++v3 )
  {
    if ( a3
      && (a2 = 32LL * v3, v7 = *(_DWORD *)((char *)this + a2 + 56), a3 >= v7)
      && a3 < *(_DWORD *)((char *)this + a2 + 60) + v7 )
    {
      *(_OWORD *)((char *)this + 12) = *(_OWORD *)((char *)this + a2 + 48);
      v8 = *(_OWORD *)((char *)this + a2 + 64);
      *((_DWORD *)this + 11) = 1;
      *(_OWORD *)((char *)this + 28) = v8;
      *((_DWORD *)this + 3) = a3 - *((_DWORD *)this + 5) - 32;
    }
    else
    {
      CLogStorage::_UnmapBuffer(*((CLogStorage **)this + 22), *(LPCVOID **)((char *)this + 32 * v3 + 68), 0);
    }
  }
  v9 = *((_DWORD *)this + 11);
  *((_DWORD *)this + 2) = 0;
  if ( !a3 )
  {
    if ( v9 )
    {
      v10 = (LPCVOID *)*((_QWORD *)this + 4);
      v11 = (CLogStorage *)*((_QWORD *)this + 22);
      *((_DWORD *)this + 11) = 0;
      CLogStorage::_UnmapBuffer(v11, v10, 0);
    }
    return 0;
  }
  *(_DWORD *)this = a3;
  if ( v9 )
  {
    if ( !i )
      i = **((_DWORD **)this + 22);
    FirstPage = CBuffer::GetFirstPage(*((CBuffer **)this + 4), a2, i, 0, 0);
    if ( !FirstPage || *((_DWORD *)FirstPage + 2) != i )
    {
      pExceptionObject = -2147479510;
      throw &pExceptionObject;
    }
    v14 = *((unsigned int *)this + 3);
    if ( *(_DWORD *)((char *)FirstPage + v14 + 32) != *(_DWORD *)this )
    {
      pExceptionObject = -2147479510;
      throw &pExceptionObject;
    }
    *((_DWORD *)this + 1) = *(_DWORD *)((char *)FirstPage + v14 + 40);
  }
  else
  {
    CReadMap::_SetUpResidue(this, i);
  }
  v15 = *((_DWORD *)this + 1);
  if ( (unsigned __int64)(unsigned int)(v15 + *(_DWORD *)this) + 24 < (unsigned int)(*((_DWORD *)this + 5)
                                                                                   + *((_DWORD *)this + 6)) )
  {
    *((_DWORD *)this + 4) = v15 + 24;
    v16 = 32LL * *((unsigned int *)this + 2);
    *(_OWORD *)((char *)this + v16 + 48) = *(_OWORD *)((char *)this + 12);
    *(_OWORD *)((char *)this + v16 + 64) = *(_OWORD *)((char *)this + 28);
    ++*((_DWORD *)this + 2);
    *((_DWORD *)this + 11) = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d160  push    rbx
0x18000d162  push    rbp
0x18000d163  push    rsi
0x18000d164  push    rdi
0x18000d165  sub     rsp, 38h
0x18000d169  xor     ebp, ebp
0x18000d16b  mov     edi, r8d
0x18000d16e  mov     esi, edx
0x18000d170  mov     rbx, rcx
0x18000d173  cmp     [rcx+8], ebp
0x18000d176  jbe     short loc_18000D1D9
0x18000d178  test    edi, edi
0x18000d17a  jz      short loc_18000D1B8
0x18000d17c  mov     edx, ebp
0x18000d17e  shl     rdx, 5
0x18000d182  mov     ecx, [rdx+rbx+38h]
0x18000d186  cmp     edi, ecx
0x18000d188  jb      short loc_18000D1B8
0x18000d18a  add     ecx, [rdx+rbx+3Ch]
0x18000d18e  cmp     edi, ecx
0x18000d190  jnb     short loc_18000D1B8
0x18000d192  movups  xmm0, xmmword ptr [rdx+rbx+30h]
0x18000d197  mov     eax, edi
0x18000d199  movups  xmmword ptr [rbx+0Ch], xmm0
0x18000d19d  movups  xmm1, xmmword ptr [rdx+rbx+40h]
0x18000d1a2  mov     dword ptr [rbx+2Ch], 1
0x18000d1a9  movups  xmmword ptr [rbx+1Ch], xmm1
0x18000d1ad  sub     eax, [rbx+14h]
0x18000d1b0  sub     eax, 20h ; ' '
0x18000d1b3  mov     [rbx+0Ch], eax
0x18000d1b6  jmp     short loc_18000D1D2
0x18000d1b8  mov     rcx, [rbx+0B0h]; this
0x18000d1bf  xor     r8d, r8d; int
0x18000d1c2  mov     edx, ebp
0x18000d1c4  shl     rdx, 5
0x18000d1c8  mov     rdx, [rdx+rbx+44h]; struct CBuffer *
0x18000d1cd  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000d1d2  inc     ebp
0x18000d1d4  cmp     ebp, [rbx+8]
0x18000d1d7  jb      short loc_18000D178
0x18000d1d9  mov     eax, [rbx+2Ch]
0x18000d1dc  mov     dword ptr [rbx+8], 0
0x18000d1e3  test    edi, edi
0x18000d1e5  jnz     short loc_18000D20C
0x18000d1e7  test    eax, eax
0x18000d1e9  jz      short loc_18000D201
0x18000d1eb  mov     rdx, [rbx+20h]; struct CBuffer *
0x18000d1ef  xor     r8d, r8d; int
0x18000d1f2  mov     rcx, [rbx+0B0h]; this
0x18000d1f9  mov     [rbx+2Ch], edi
0x18000d1fc  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000d201  xor     eax, eax
0x18000d203  add     rsp, 38h
0x18000d207  pop     rdi
0x18000d208  pop     rsi
0x18000d209  pop     rbp
0x18000d20a  pop     rbx
0x18000d20b  retn
0x18000d20c  mov     [rbx], edi
0x18000d20e  test    eax, eax
0x18000d210  jnz     short loc_18000D21E
0x18000d212  mov     edx, esi; unsigned int
0x18000d214  mov     rcx, rbx; this
0x18000d217  call    ?_SetUpResidue@CReadMap@@AEAAXK@Z; CReadMap::_SetUpResidue(ulong)
0x18000d21c  jmp     short loc_18000D262
0x18000d21e  test    esi, esi
0x18000d220  jnz     short loc_18000D22B
0x18000d222  mov     rax, [rbx+0B0h]
0x18000d229  mov     esi, [rax]
0x18000d22b  mov     rcx, [rbx+20h]; this
0x18000d22f  xor     r9d, r9d; unsigned int *
0x18000d232  mov     r8d, esi; unsigned int
0x18000d235  mov     [rsp+58h+var_38], 0; unsigned int *
0x18000d23e  call    ?GetFirstPage@CBuffer@@QEAAPEAU_RECORDPAGE@@HKPEAK0@Z; CBuffer::GetFirstPage(int,ulong,ulong *,ulong *)
0x18000d243  mov     rcx, rax
0x18000d246  test    rax, rax
0x18000d249  jz      short loc_18000D2B3
0x18000d24b  cmp     [rax+8], esi
0x18000d24e  jnz     short loc_18000D2B3
0x18000d250  mov     edx, [rbx+0Ch]
0x18000d253  mov     eax, [rbx]
0x18000d255  cmp     [rdx+rcx+20h], eax
0x18000d259  jnz     short loc_18000D2CD
0x18000d25b  mov     eax, [rdx+rcx+28h]
0x18000d25f  mov     [rbx+4], eax
0x18000d262  mov     eax, [rbx]
0x18000d264  mov     edx, [rbx+18h]
0x18000d267  mov     r8d, [rbx+4]
0x18000d26b  add     eax, r8d
0x18000d26e  add     edx, [rbx+14h]
0x18000d271  add     rax, 18h
0x18000d275  cmp     rax, rdx
0x18000d278  jnb     short loc_18000D2A9
0x18000d27a  lea     eax, [r8+18h]
0x18000d27e  mov     [rbx+10h], eax
0x18000d281  mov     eax, [rbx+8]
0x18000d284  movups  xmm0, xmmword ptr [rbx+0Ch]
0x18000d288  shl     rax, 5
0x18000d28c  movups  xmmword ptr [rax+rbx+30h], xmm0
0x18000d291  movups  xmm1, xmmword ptr [rbx+1Ch]
0x18000d295  movups  xmmword ptr [rax+rbx+40h], xmm1
0x18000d29a  inc     dword ptr [rbx+8]
0x18000d29d  mov     dword ptr [rbx+2Ch], 0
0x18000d2a4  jmp     loc_18000D201
0x18000d2a9  mov     eax, 1
0x18000d2ae  jmp     loc_18000D203
0x18000d2b3  lea     rdx, _TI1K; pThrowInfo
0x18000d2ba  mov     [rsp+58h+pExceptionObject], 8000102Ah
0x18000d2c2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000d2c7  call    _CxxThrowException_0
0x18000d2cd  lea     rdx, _TI1K; pThrowInfo
0x18000d2d4  mov     [rsp+58h+pExceptionObject], 8000102Ah
0x18000d2dc  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18000d2e1  call    _CxxThrowException_0
```

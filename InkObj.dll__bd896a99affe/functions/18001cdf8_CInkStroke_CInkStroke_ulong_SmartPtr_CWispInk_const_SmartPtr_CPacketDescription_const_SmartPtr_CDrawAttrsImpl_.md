# CInkStroke::CInkStroke(ulong,SmartPtr<CWispInk> const &,SmartPtr<CPacketDescription> const &,SmartPtr<CDrawAttrsImpl> const &)

- ea: `0x18001cdf8`
- end: `0x18001d306`
- name: `??0CInkStroke@@QEAA@KAEBV?$SmartPtr@VCWispInk@@@@AEBV?$SmartPtr@VCPacketDescription@@@@AEBV?$SmartPtr@VCDrawAttrsImpl@@@@@Z`
- size: `1294`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003ab9c`
- `0x18003d030`
- `0x18008e5d8`

## callees

- `0x1800017a8`
- `0x180002740`
- `0x180003ba0`
- `0x180006b80`
- `0x18001cdf8`
- `0x1800325b8`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x180044ab0`
- `0x18009a3f0`
- `0x18009b010`
- `0x18009fd10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ce6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cf4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ce6f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cf4b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001d0a4`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001d0a4`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d0e8`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d162`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d0e8`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18001d162`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CInkStroke::CInkStroke(__int64 a1, int a2, _BOOL8 a3, __int64 *a4, __int64 *a5)
{
  char *v7; // rdi
  void **v8; // rbx
  __int64 v9; // rax
  _DWORD *v10; // rcx
  unsigned int v11; // r12d
  unsigned int v12; // r13d
  void *v13; // r12
  LPVOID v14; // rax
  unsigned int i; // esi
  __int64 v16; // rcx
  __int64 v17; // rax
  BytesArray *v19; // rax
  char v20; // bl
  __int64 v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-40h]
  _BYTE v23[40]; // [rsp+38h] [rbp-28h] BYREF
  int v24; // [rsp+A0h] [rbp+40h]
  int pExceptionObject; // [rsp+A8h] [rbp+48h] BYREF
  __int64 *v26; // [rsp+B0h] [rbp+50h]

  v26 = (__int64 *)a3;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = a2;
  v22 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(v22 + 4) )
  {
    Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
    {
      `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
      dwFlags = 0;
      `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
      atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
      Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
    }
  }
  if ( `WinHeap::GetDefault'::`2'::s_WinHeap )
    v7 = (char *)HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 0x108u);
  else
    v7 = 0;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &CInkStroke::CInkStrokeImpl::`vftable';
    v8 = (void **)(v7 + 16);
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    v9 = *a4;
    *((_QWORD *)v7 + 5) = *a4;
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    *((_QWORD *)v7 + 6) = 0;
    *((_QWORD *)v7 + 7) = 0;
    *((_QWORD *)v7 + 8) = 0;
    *((_QWORD *)v7 + 9) = 0;
    *((_QWORD *)v7 + 10) = 0;
    v10 = *(_DWORD **)(*((_QWORD *)v7 + 5) + 16LL);
    v11 = v10[5];
    pExceptionObject = v11;
    v24 = v10[8];
    v12 = v24 + v11;
    if ( v24 + v11 < v11 )
    {
      pExceptionObject = -2147418113;
      throw (long *)&pExceptionObject;
    }
    if ( v12 )
    {
      if ( 32 * (unsigned __int64)v12 > 0xFFFFFFFF )
        goto LABEL_56;
      v13 = *v8;
      if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *(_DWORD *)(v22 + 4) )
      {
        Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
        {
          `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
          dwFlags = 0;
          `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
          atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
          Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        }
      }
      v10 = `WinHeap::GetDefault'::`2'::s_WinHeap;
      if ( !`WinHeap::GetDefault'::`2'::s_WinHeap
        || (v13
          ? (v14 = HeapReAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, v13, 32LL * v12))
          : (v14 = HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 32LL * v12)),
            !v14) )
      {
LABEL_56:
        if ( *((_QWORD *)v7 + 3) )
          Allocator<BytesArray>::Destruct(v10, *v8);
        if ( *v8 )
        {
          WinFree(*v8);
          *v8 = 0;
        }
        *((_QWORD *)v7 + 3) = 0;
        *((_QWORD *)v7 + 4) = 0;
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      *v8 = v14;
      v11 = pExceptionObject;
    }
    else if ( *v8 )
    {
      WinFree(*v8);
      *v8 = 0;
    }
    *((_QWORD *)v7 + 4) = v12;
    if ( dword_18016DC60 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_18016DC60);
      if ( dword_18016DC60 == -1 )
      {
        BytesArray::BytesArray((BytesArray *)qword_18016DC68, 4u, 0, 0);
        atexit(CPacketList::CPacketList_::_2_::_dynamic_atexit_destructor_for__pkt__);
        Init_thread_footer(&dword_18016DC60);
      }
    }
    for ( i = 0; i < v11; ++i )
    {
      if ( !(unsigned __int8)Vector<BytesArray,Allocator<BytesArray>>::push_back(v7 + 16, qword_18016DC68) )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
    }
    if ( v24 )
    {
      v19 = BytesArray::BytesArray((BytesArray *)v23, (unsigned int)(v24 + 7) >> 3, 0, 0);
      v20 = Vector<BytesArray,Allocator<BytesArray>>::push_back(v7 + 16, v19);
      Vector<unsigned char,BasicAllocator<unsigned char>>::~Vector<unsigned char,BasicAllocator<unsigned char>>(v23);
      if ( !v20 )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
    }
    if ( (unsigned __int64)v11 > *((_QWORD *)v7 + 7) )
    {
      if ( !(unsigned __int8)Vector<unsigned char,BasicAllocator<unsigned char>>::reserve(v7 + 48, v11) )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      BasicAllocator<unsigned char>::Construct(
        v21,
        *((_QWORD *)v7 + 7) + *((_QWORD *)v7 + 6),
        &dword_180125D7C,
        v11 - *((_QWORD *)v7 + 7));
    }
    *((_QWORD *)v7 + 7) = v11;
    *((_QWORD *)v7 + 11) = 0;
    *((_QWORD *)v7 + 12) = 0;
    *((_QWORD *)v7 + 13) = 0;
    *((_QWORD *)v7 + 14) = 0;
    *((_QWORD *)v7 + 15) = 0;
    *((_QWORD *)v7 + 16) = 0;
    v16 = *a5;
    *((_QWORD *)v7 + 17) = *a5;
    if ( v16 )
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
    v17 = *v26;
    *((_QWORD *)v7 + 18) = *v26;
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
    *((_QWORD *)v7 + 19) = 0;
    *((_QWORD *)v7 + 20) = 0;
    *((_DWORD *)v7 + 42) = 0;
    *((_QWORD *)v7 + 23) = 0;
    *((_QWORD *)v7 + 22) = 0;
    v7[200] = 0;
    *((_QWORD *)v7 + 26) = 0;
    *((_QWORD *)v7 + 27) = 0;
    CXform::SetXform((CXform *)(v7 + 216), 0, a3);
    *(_OWORD *)(v7 + 228) = xmmword_180121300;
    *(_OWORD *)(v7 + 244) = xmmword_180121300;
    *((_DWORD *)v7 + 65) = 0;
    *((_QWORD *)v7 + 24) = 0;
    v7[224] = 1;
  }
  else
  {
    v7 = 0;
  }
  *(_QWORD *)(a1 + 16) = v7;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
  return a1;
}

```

## disassembly

```asm
0x18001cdf8  mov     [rsp-38h+arg_18], rbx
0x18001cdfd  mov     [rsp-38h+arg_10], r8
0x18001ce02  mov     [rsp-38h+arg_0], rcx
0x18001ce07  push    rbp
0x18001ce08  push    rsi
0x18001ce09  push    rdi
0x18001ce0a  push    r12
0x18001ce0c  push    r13
0x18001ce0e  push    r14
0x18001ce10  push    r15
0x18001ce12  mov     rbp, rsp
0x18001ce15  sub     rsp, 60h
0x18001ce19  mov     rsi, r9
0x18001ce1c  mov     r15, rcx
0x18001ce1f  xor     r13d, r13d
0x18001ce22  mov     [rcx], r13
0x18001ce25  mov     [rcx+8], edx
0x18001ce28  mov     ecx, 4
0x18001ce2d  mov     edx, cs:_tls_index
0x18001ce33  mov     rax, gs:58h
0x18001ce3c  mov     rax, [rax+rdx*8]
0x18001ce40  mov     [rbp+var_40], rax
0x18001ce44  mov     eax, [rax+rcx]
0x18001ce47  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001ce4d  jg      loc_18001D0B7
0x18001ce53  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18001ce5a  test    rcx, rcx
0x18001ce5d  jz      loc_18001D0AF
0x18001ce63  mov     r8d, 108h; dwBytes
0x18001ce69  mov     edx, cs:dwFlags; dwFlags
0x18001ce6f  call    cs:__imp_HeapAlloc
0x18001ce75  mov     rdi, rax
0x18001ce78  mov     [rbp+var_38], rdi
0x18001ce7c  test    rdi, rdi
0x18001ce7f  jz      loc_18001D2FD
0x18001ce85  mov     [rdi+8], r13d
0x18001ce89  lea     rax, ??_7CInkStrokeImpl@CInkStroke@@6B@; const CInkStroke::CInkStrokeImpl::`vftable'
0x18001ce90  mov     [rdi], rax
0x18001ce93  lea     rbx, [rdi+10h]
0x18001ce97  mov     [rbp+var_30], rbx
0x18001ce9b  mov     [rbx], r13
0x18001ce9e  mov     [rbx+8], r13
0x18001cea2  mov     [rbx+10h], r13
0x18001cea6  mov     rax, [rsi]
0x18001cea9  mov     [rbx+18h], rax
0x18001cead  test    rax, rax
0x18001ceb0  jz      short loc_18001CEB6
0x18001ceb2  lock inc dword ptr [rax+8]
0x18001ceb6  lea     r14, [rbx+20h]
0x18001ceba  mov     [r14], r13
0x18001cebd  mov     [r14+8], r13
0x18001cec1  mov     [r14+10h], r13
0x18001cec5  mov     [rbx+38h], r13
0x18001cec9  mov     [rbx+40h], r13
0x18001cecd  mov     rax, [rbx+18h]
0x18001ced1  mov     rcx, [rax+10h]
0x18001ced5  mov     r12d, [rcx+14h]
0x18001ced9  mov     [rbp+pExceptionObject], r12d
0x18001cedd  mov     eax, [rcx+20h]
0x18001cee0  mov     dword ptr [rbp+arg_0], eax
0x18001cee3  lea     r13d, [rax+r12]
0x18001cee7  cmp     r13d, r12d
0x18001ceea  jb      loc_18001D112
0x18001cef0  test    r13d, r13d
0x18001cef3  jz      loc_18001D1CF
0x18001cef9  mov     esi, r13d
0x18001cefc  shl     rsi, 5
0x18001cf00  mov     eax, 0FFFFFFFFh
0x18001cf05  cmp     rsi, rax
0x18001cf08  ja      loc_18001D18C
0x18001cf0e  mov     r12, [rbx]
0x18001cf11  mov     rax, [rbp+var_40]
0x18001cf15  mov     ecx, 4
0x18001cf1a  mov     eax, [rax+rcx]
0x18001cf1d  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x18001cf23  jg      loc_18001D12A
0x18001cf29  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x18001cf30  test    rcx, rcx
0x18001cf33  jz      loc_18001D18C
0x18001cf39  mov     edx, cs:dwFlags; dwFlags
0x18001cf3f  test    r12, r12
0x18001cf42  jnz     loc_18001D09E
0x18001cf48  mov     r8, rsi; dwBytes
0x18001cf4b  call    cs:__imp_HeapAlloc
0x18001cf51  test    rax, rax
0x18001cf54  jz      loc_18001D18C
0x18001cf5a  mov     [rbx], rax
0x18001cf5d  mov     r12d, [rbp+pExceptionObject]
0x18001cf61  mov     eax, r13d
0x18001cf64  mov     [rbx+10h], rax
0x18001cf68  mov     ecx, cs:_tls_index
0x18001cf6e  mov     rax, gs:58h
0x18001cf77  mov     rax, [rax+rcx*8]
0x18001cf7b  mov     ecx, 4
0x18001cf80  mov     eax, [rcx+rax]
0x18001cf83  cmp     cs:dword_18016DC60, eax
0x18001cf89  jg      loc_18001D1EC
0x18001cf8f  xor     r13d, r13d
0x18001cf92  mov     esi, r13d
0x18001cf95  cmp     esi, r12d
0x18001cf98  jb      loc_18001D239
0x18001cf9e  mov     edx, dword ptr [rbp+arg_0]
0x18001cfa1  test    edx, edx
0x18001cfa3  jnz     loc_18001D26B
0x18001cfa9  mov     ebx, r12d
0x18001cfac  cmp     rbx, [r14+8]
0x18001cfb0  ja      loc_18001D2B7
0x18001cfb6  mov     [r14+8], rbx
0x18001cfba  mov     [rdi+58h], r13
0x18001cfbe  mov     [rdi+60h], r13
0x18001cfc2  mov     [rdi+68h], r13
0x18001cfc6  mov     [rdi+70h], r13
0x18001cfca  mov     [rdi+78h], r13
0x18001cfce  mov     [rdi+80h], r13
0x18001cfd5  mov     rax, [rbp+arg_20]
0x18001cfd9  mov     rcx, [rax]
0x18001cfdc  mov     [rdi+88h], rcx
0x18001cfe3  test    rcx, rcx
0x18001cfe6  jz      short loc_18001CFEC
0x18001cfe8  lock inc dword ptr [rcx+8]
0x18001cfec  mov     rax, [rbp+arg_10]
0x18001cff0  mov     rax, [rax]
0x18001cff3  mov     [rdi+90h], rax
0x18001cffa  test    rax, rax
0x18001cffd  jz      short loc_18001D003
0x18001cfff  lock inc dword ptr [rax+8]
0x18001d003  mov     [rdi+98h], r13
0x18001d00a  mov     [rdi+0A0h], r13
0x18001d011  mov     [rdi+0A8h], r13d
0x18001d018  mov     [rdi+0B8h], r13
0x18001d01f  mov     [rdi+0B0h], r13
0x18001d026  mov     [rdi+0C8h], r13b
0x18001d02d  mov     [rdi+0D0h], r13
0x18001d034  lea     rcx, [rdi+0D8h]; this
0x18001d03b  mov     [rbp+arg_0], rcx
0x18001d03f  mov     [rcx], r13
0x18001d042  xor     edx, edx; struct tagXFORM *
0x18001d044  call    ?SetXform@CXform@@IEAAXPEBUtagXFORM@@_N@Z; CXform::SetXform(tagXFORM const *,bool)
0x18001d049  nop
0x18001d04a  movups  xmm0, cs:xmmword_180121300
0x18001d051  movdqu  xmmword ptr [rdi+0E4h], xmm0
0x18001d059  movdqu  xmmword ptr [rdi+0F4h], xmm0
0x18001d061  mov     [rdi+104h], r13d
0x18001d068  mov     [rdi+0C0h], r13
0x18001d06f  mov     byte ptr [rdi+0E0h], 1
0x18001d076  mov     [r15+10h], rdi
0x18001d07a  test    rdi, rdi
0x18001d07d  jz      short loc_18001D083
0x18001d07f  lock inc dword ptr [rdi+8]
0x18001d083  mov     rax, r15
0x18001d086  mov     rbx, [rsp+60h+arg_18]
0x18001d08e  add     rsp, 60h
0x18001d092  pop     r15
0x18001d094  pop     r14
0x18001d096  pop     r13
0x18001d098  pop     r12
0x18001d09a  pop     rdi
0x18001d09b  pop     rsi
0x18001d09c  pop     rbp
0x18001d09d  retn
0x18001d09e  mov     r9, rsi; dwBytes
0x18001d0a1  mov     r8, r12; lpMem
0x18001d0a4  call    cs:__imp_HeapReAlloc
0x18001d0aa  jmp     loc_18001CF51
0x18001d0af  mov     rdi, r13
0x18001d0b2  jmp     loc_18001CE78
0x18001d0b7  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d0be  call    _Init_thread_header
0x18001d0c3  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18001d0ca  jnz     loc_18001CE53
0x18001d0d0  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, r13; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d0d7  mov     cs:dwFlags, r13d
0x18001d0de  xor     r8d, r8d; dwMaximumSize
0x18001d0e1  mov     edx, 10000h; dwInitialSize
0x18001d0e6  xor     ecx, ecx; flOptions
0x18001d0e8  call    cs:__imp_HeapCreate
0x18001d0ee  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d0f5  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001d0fc  call    atexit
0x18001d101  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d108  call    _Init_thread_footer
0x18001d10d  jmp     loc_18001CE53
0x18001d112  mov     [rbp+pExceptionObject], 8000FFFFh
0x18001d119  lea     rdx, _TI1J; pThrowInfo
0x18001d120  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d124  call    _CxxThrowException_0
0x18001d12a  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d131  call    _Init_thread_header
0x18001d136  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x18001d13d  jnz     loc_18001CF29
0x18001d143  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, 0; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d14e  mov     cs:dwFlags, 0
0x18001d158  xor     r8d, r8d; dwMaximumSize
0x18001d15b  mov     edx, 10000h; dwInitialSize
0x18001d160  xor     ecx, ecx; flOptions
0x18001d162  call    cs:__imp_HeapCreate
0x18001d168  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18001d16f  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x18001d176  call    atexit
0x18001d17b  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18001d182  call    _Init_thread_footer
0x18001d187  jmp     loc_18001CF29
0x18001d18c  mov     r8, [rbx+8]
0x18001d190  xor     edi, edi
0x18001d192  test    r8, r8
0x18001d195  jz      short loc_18001D19F
0x18001d197  mov     rdx, [rbx]
0x18001d19a  call    ?Destruct@?$Allocator@VBytesArray@@@@QEAAXPEAVBytesArray@@_K@Z; Allocator<BytesArray>::Destruct(BytesArray *,unsigned __int64)
0x18001d19f  mov     rcx, [rbx]; void *
0x18001d1a2  test    rcx, rcx
0x18001d1a5  jz      short loc_18001D1AF
0x18001d1a7  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18001d1ac  mov     [rbx], rdi
0x18001d1af  mov     [rbx+8], rdi
0x18001d1b3  mov     [rbx+10h], rdi
0x18001d1b7  mov     [rbp+pExceptionObject], 8007000Eh
0x18001d1be  lea     rdx, _TI1J; pThrowInfo
0x18001d1c5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d1c9  call    _CxxThrowException_0
0x18001d1cf  mov     rcx, [rbx]; void *
0x18001d1d2  test    rcx, rcx
0x18001d1d5  jz      loc_18001CF61
0x18001d1db  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x18001d1e0  mov     qword ptr [rbx], 0
0x18001d1e7  jmp     loc_18001CF61
0x18001d1ec  lea     rcx, dword_18016DC60
0x18001d1f3  call    _Init_thread_header
0x18001d1f8  cmp     cs:dword_18016DC60, 0FFFFFFFFh
0x18001d1ff  jnz     loc_18001CF8F
0x18001d205  xor     r9d, r9d; unsigned int
0x18001d208  xor     r8d, r8d; unsigned __int8 *
0x18001d20b  lea     edx, [r9+4]; unsigned int
0x18001d20f  lea     rcx, qword_18016DC68; this
0x18001d216  call    ??0BytesArray@@QEAA@KPEBEK@Z; BytesArray::BytesArray(ulong,uchar const *,ulong)
0x18001d21b  lea     rcx, _CPacketList__CPacketList____2____dynamic_atexit_destructor_for__pkt__; void (__cdecl *)()
0x18001d222  call    atexit
0x18001d227  nop
0x18001d228  lea     rcx, dword_18016DC60
0x18001d22f  call    _Init_thread_footer
0x18001d234  jmp     loc_18001CF8F
0x18001d239  lea     rdx, qword_18016DC68
0x18001d240  mov     rcx, rbx
0x18001d243  call    ?push_back@?$Vector@VBytesArray@@V?$Allocator@VBytesArray@@@@@@QEAA_NAEBVBytesArray@@@Z; Vector<BytesArray,Allocator<BytesArray>>::push_back(BytesArray const &)
0x18001d248  test    al, al
0x18001d24a  jz      short loc_18001D253
0x18001d24c  inc     esi
0x18001d24e  jmp     loc_18001CF95
0x18001d253  mov     [rbp+pExceptionObject], 8007000Eh
0x18001d25a  lea     rdx, _TI1J; pThrowInfo
0x18001d261  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d265  call    _CxxThrowException_0
0x18001d26b  add     edx, 7
0x18001d26e  shr     edx, 3; unsigned int
0x18001d271  xor     r9d, r9d; unsigned int
0x18001d274  xor     r8d, r8d; unsigned __int8 *
0x18001d277  lea     rcx, [rbp+var_28]; this
0x18001d27b  call    ??0BytesArray@@QEAA@KPEBEK@Z; BytesArray::BytesArray(ulong,uchar const *,ulong)
0x18001d280  nop
0x18001d281  mov     rdx, rax
0x18001d284  mov     rcx, rbx
0x18001d287  call    ?push_back@?$Vector@VBytesArray@@V?$Allocator@VBytesArray@@@@@@QEAA_NAEBVBytesArray@@@Z; Vector<BytesArray,Allocator<BytesArray>>::push_back(BytesArray const &)
0x18001d28c  mov     bl, al
0x18001d28e  lea     rcx, [rbp+var_28]
0x18001d292  call    ??1?$Vector@EV?$BasicAllocator@E@@@@QEAA@XZ; Vector<uchar,BasicAllocator<uchar>>::~Vector<uchar,BasicAllocator<uchar>>(void)
0x18001d297  test    bl, bl
0x18001d299  jnz     loc_18001CFA9
0x18001d29f  mov     [rbp+pExceptionObject], 8007000Eh
0x18001d2a6  lea     rdx, _TI1J; pThrowInfo
0x18001d2ad  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d2b1  call    _CxxThrowException_0
0x18001d2b7  mov     rdx, rbx
0x18001d2ba  mov     rcx, r14
0x18001d2bd  call    ?reserve@?$Vector@EV?$BasicAllocator@E@@@@QEAA_N_K@Z; Vector<uchar,BasicAllocator<uchar>>::reserve(unsigned __int64)
0x18001d2c2  test    al, al
0x18001d2c4  jnz     short loc_18001D2DE
0x18001d2c6  mov     [rbp+pExceptionObject], 8007000Eh
0x18001d2cd  lea     rdx, _TI1J; pThrowInfo
0x18001d2d4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d2d8  call    _CxxThrowException_0
0x18001d2de  mov     r9, rbx
0x18001d2e1  sub     r9, [r14+8]
0x18001d2e5  mov     rdx, [r14]
0x18001d2e8  add     rdx, [r14+8]
0x18001d2ec  lea     r8, dword_180125D7C
0x18001d2f3  call    ?Construct@?$BasicAllocator@E@@QEAAXPEAEAEBE_K@Z; BasicAllocator<uchar>::Construct(uchar *,uchar const &,unsigned __int64)
0x18001d2f8  jmp     loc_18001CFB6
0x18001d2fd  mov     rdi, r13
0x18001d300  jmp     loc_18001D076
```

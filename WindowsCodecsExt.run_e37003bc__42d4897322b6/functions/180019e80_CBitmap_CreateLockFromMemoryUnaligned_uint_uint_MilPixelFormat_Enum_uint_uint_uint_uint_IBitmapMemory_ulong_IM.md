# CBitmap::CreateLockFromMemoryUnaligned(uint,uint,MilPixelFormat::Enum,uint,uint,uint,uint,IBitmapMemory *,ulong,IMILBitmapLock * *)

- ea: `0x180019e80`
- end: `0x180019ffb`
- name: `?CreateLockFromMemoryUnaligned@CBitmap@@IEAAJIIW4Enum@MilPixelFormat@@IIIIPEAUIBitmapMemory@@KPEAPEAUIMILBitmapLock@@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019bc0`

## callees

- `0x1800171c4`
- `0x180019600`
- `0x180019e80`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CBitmap::CreateLockFromMemoryUnaligned(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        int a10,
        __int64 *a11)
{
  _DWORD *v15; // rax
  _DWORD *v16; // rbx
  int v17; // eax
  unsigned int v18; // edi

  v15 = operator new(0x78u);
  v16 = v15;
  if ( v15 )
  {
    v15[2] = 0;
    *(_QWORD *)v15 = &CMILCOMBase::`vftable';
    _InterlockedIncrement(&g_cActiveObjects);
    v15[8] = 0;
    *((_QWORD *)v15 + 10) = 0;
    *((_QWORD *)v15 + 2) = &CBitmapLockUnaligned::`vftable'{for `IMILBitmapLock'};
    *((_QWORD *)v15 + 7) = 0;
    *((_QWORD *)v15 + 3) = &CBitmapLockUnaligned::`vftable'{for `IWICBitmapLock'};
    *(_QWORD *)v15 = &CBitmapLockUnaligned::`vftable'{for `CMILCOMBase'};
    *((_QWORD *)v15 + 11) = 0;
    v15[28] = 0;
    CEncodingStream::AddRef((CEncodingStream *)v15);
    v17 = CBitmapLockUnaligned::HrInit(v16, (a1 + 16) & -(__int64)(a1 != 0), a2, a3, a4, a7, a8, a9, a10, a5, a6);
    v18 = v17;
    if ( v17 >= 0 )
    {
      if ( (a10 & 2) != 0 && (*(_DWORD *)(a1 + 96))++ == -1 )
        *(_DWORD *)(a1 + 96) = 1;
      *a11 = (unsigned __int64)(v16 + 4) & -(__int64)(v16 != 0);
    }
    else
    {
      if ( g_doStackCaptures )
        DoStackCapture(v17);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  else
  {
    v18 = -2147024882;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024882);
  }
  return v18;
}

```

## disassembly

```asm
0x180019e80  push    rbx
0x180019e82  push    rbp
0x180019e83  push    rsi
0x180019e84  push    rdi
0x180019e85  push    r14
0x180019e87  push    r15
0x180019e89  sub     rsp, 78h
0x180019e8d  mov     rsi, rcx
0x180019e90  mov     edi, r9d
0x180019e93  mov     ecx, 78h ; 'x'; Size
0x180019e98  mov     r14d, r8d
0x180019e9b  mov     r15d, edx
0x180019e9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019ea3  mov     rbx, rax
0x180019ea6  test    rax, rax
0x180019ea9  jz      loc_180019FD7
0x180019eaf  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x180019eb6  mov     dword ptr [rbx+8], 0
0x180019ebd  mov     [rbx], rax
0x180019ec0  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180019ec7  lea     rdx, ??_7CBitmapLockUnaligned@@6BCMILCOMBase@@@; const CBitmapLockUnaligned::`vftable'{for `CMILCOMBase'}
0x180019ece  mov     dword ptr [rbx+20h], 0
0x180019ed5  lea     rax, ??_7CBitmapLockUnaligned@@6BIMILBitmapLock@@@; const CBitmapLockUnaligned::`vftable'{for `IMILBitmapLock'}
0x180019edc  mov     qword ptr [rbx+50h], 0
0x180019ee4  mov     [rbx+10h], rax
0x180019ee8  mov     rcx, rbx
0x180019eeb  lea     rax, ??_7CBitmapLockUnaligned@@6BIWICBitmapLock@@@; const CBitmapLockUnaligned::`vftable'{for `IWICBitmapLock'}
0x180019ef2  mov     qword ptr [rbx+38h], 0
0x180019efa  mov     [rbx+18h], rax
0x180019efe  mov     rax, [rdx+8]
0x180019f02  mov     [rbx], rdx
0x180019f05  mov     qword ptr [rbx+58h], 0
0x180019f0d  mov     dword ptr [rbx+70h], 0
0x180019f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f19  mov     ebp, [rsp+0A8h+arg_48]
0x180019f20  lea     rcx, [rsi+10h]
0x180019f24  mov     rax, rsi
0x180019f27  mov     r9d, r14d
0x180019f2a  neg     rax
0x180019f2d  mov     r8d, r15d
0x180019f30  mov     eax, [rsp+0A8h+arg_28]
0x180019f37  mov     [rsp+0A8h+var_58], eax
0x180019f3b  sbb     rdx, rdx
0x180019f3e  mov     eax, [rsp+0A8h+arg_20]
0x180019f45  and     rdx, rcx
0x180019f48  mov     [rsp+0A8h+var_60], eax
0x180019f4c  mov     rcx, rbx
0x180019f4f  mov     rax, [rsp+0A8h+arg_40]
0x180019f57  mov     [rsp+0A8h+var_68], ebp
0x180019f5b  mov     [rsp+0A8h+var_70], rax
0x180019f60  mov     eax, [rsp+0A8h+arg_38]
0x180019f67  mov     [rsp+0A8h+var_78], eax
0x180019f6b  mov     eax, [rsp+0A8h+arg_30]
0x180019f72  mov     [rsp+0A8h+var_80], eax
0x180019f76  mov     [rsp+0A8h+var_88], edi
0x180019f7a  call    ?HrInit@CBitmapLockUnaligned@@QEAAJPEAUIMILBitmap@@IIW4Enum@MilPixelFormat@@IIPEAUIBitmapMemory@@KII@Z; CBitmapLockUnaligned::HrInit(IMILBitmap *,uint,uint,MilPixelFormat::Enum,uint,uint,IBitmapMemory *,ulong,uint,uint)
0x180019f7f  mov     edi, eax
0x180019f81  test    eax, eax
0x180019f83  jns     short loc_180019FAA
0x180019f85  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180019f8c  jz      short loc_180019FA6
0x180019f8e  mov     ecx, eax; int
0x180019f90  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180019f95  mov     rax, [rbx]
0x180019f98  mov     rcx, rbx
0x180019f9b  mov     rax, [rax+10h]
0x180019f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fa4  jmp     short loc_180019FEC
0x180019fa6  test    eax, eax
0x180019fa8  js      short loc_180019F95
0x180019faa  test    bpl, 2
0x180019fae  jz      short loc_180019FBD
0x180019fb0  add     dword ptr [rsi+60h], 1
0x180019fb4  jnz     short loc_180019FBD
0x180019fb6  mov     dword ptr [rsi+60h], 1
0x180019fbd  lea     rax, [rbx+10h]
0x180019fc1  neg     rbx
0x180019fc4  sbb     rcx, rcx
0x180019fc7  and     rcx, rax
0x180019fca  mov     rax, [rsp+0A8h+arg_50]
0x180019fd2  mov     [rax], rcx
0x180019fd5  jmp     short loc_180019FEC
0x180019fd7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180019fde  mov     edi, 8007000Eh
0x180019fe3  jz      short loc_180019FEC
0x180019fe5  mov     ecx, edi; int
0x180019fe7  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180019fec  mov     eax, edi
0x180019fee  add     rsp, 78h
0x180019ff2  pop     r15
0x180019ff4  pop     r14
0x180019ff6  pop     rdi
0x180019ff7  pop     rsi
0x180019ff8  pop     rbp
0x180019ff9  pop     rbx
0x180019ffa  retn
```

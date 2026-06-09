# CBitmap::CreateLockFromMemory(uint,uint,MilPixelFormat::Enum,uint,uint,IBitmapMemory *,ulong,IMILBitmapLock * *)

- ea: `0x18001a004`
- end: `0x18001a15a`
- name: `?CreateLockFromMemory@CBitmap@@IEAAJIIW4Enum@MilPixelFormat@@IIPEAUIBitmapMemory@@KPEAPEAUIMILBitmapLock@@@Z`
- size: `342`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019bc0`
- `0x18001a190`

## callees

- `0x1800171c4`
- `0x180019894`
- `0x18001a004`
- `0x1800215e8`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CBitmap::CreateLockFromMemory(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        __int64 *a9)
{
  _DWORD *v13; // rax
  _DWORD *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi

  v13 = operator new(0x58u);
  v14 = v13;
  if ( v13 )
  {
    v13[2] = 0;
    *(_QWORD *)v13 = &CMILCOMBase::`vftable';
    _InterlockedIncrement(&g_cActiveObjects);
    v13[8] = 0;
    *(_QWORD *)v13 = &CBitmapLock::`vftable'{for `CMILCOMBase'};
    *((_QWORD *)v13 + 2) = &CBitmapLock::`vftable'{for `IMILBitmapLock'};
    *((_QWORD *)v13 + 10) = 0;
    *((_QWORD *)v13 + 3) = &CBitmapLock::`vftable'{for `IWICBitmapLock'};
    *((_QWORD *)v13 + 7) = 0;
    CEncodingStream::AddRef((CEncodingStream *)v13);
    v15 = CBitmapLock::HrInit(v14, (a1 + 16) & -(__int64)(a1 != 0), a2, a3, a4, a5, a6, a7, a8);
    v16 = v15;
    if ( v15 >= 0 )
    {
      if ( (a8 & 2) != 0 && (*(_DWORD *)(a1 + 96))++ == -1 )
        *(_DWORD *)(a1 + 96) = 1;
      *a9 = (unsigned __int64)(v14 + 4) & -(__int64)(v14 != 0);
    }
    else
    {
      if ( g_doStackCaptures )
        DoStackCapture(v15);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  else
  {
    v16 = -2147024882;
    if ( g_doStackCaptures )
      DoStackCapture(-2147024882);
  }
  return v16;
}

```

## disassembly

```asm
0x18001a004  push    rbx
0x18001a006  push    rbp
0x18001a007  push    rsi
0x18001a008  push    rdi
0x18001a009  push    r14
0x18001a00b  push    r15
0x18001a00d  sub     rsp, 68h
0x18001a011  mov     rsi, rcx
0x18001a014  mov     edi, r9d
0x18001a017  mov     ecx, 58h ; 'X'; Size
0x18001a01c  mov     r14d, r8d
0x18001a01f  mov     r15d, edx
0x18001a022  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a027  mov     rbx, rax
0x18001a02a  test    rax, rax
0x18001a02d  jz      loc_18001A136
0x18001a033  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18001a03a  mov     dword ptr [rbx+8], 0
0x18001a041  mov     [rbx], rax
0x18001a044  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18001a04b  lea     rdx, ??_7CBitmapLock@@6BCMILCOMBase@@@; const CBitmapLock::`vftable'{for `CMILCOMBase'}
0x18001a052  mov     dword ptr [rbx+20h], 0
0x18001a059  lea     rax, ??_7CBitmapLock@@6BIMILBitmapLock@@@; const CBitmapLock::`vftable'{for `IMILBitmapLock'}
0x18001a060  mov     [rbx], rdx
0x18001a063  mov     [rbx+10h], rax
0x18001a067  mov     rcx, rbx
0x18001a06a  lea     rax, ??_7CBitmapLock@@6BIWICBitmapLock@@@; const CBitmapLock::`vftable'{for `IWICBitmapLock'}
0x18001a071  mov     qword ptr [rbx+50h], 0
0x18001a079  mov     [rbx+18h], rax
0x18001a07d  mov     rax, [rdx+8]
0x18001a081  mov     qword ptr [rbx+38h], 0
0x18001a089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a08e  mov     ebp, [rsp+98h+arg_38]
0x18001a095  lea     rcx, [rsi+10h]
0x18001a099  mov     [rsp+98h+var_58], ebp
0x18001a09d  mov     rax, rsi
0x18001a0a0  neg     rax
0x18001a0a3  mov     r9d, r14d
0x18001a0a6  mov     rax, [rsp+98h+arg_30]
0x18001a0ae  mov     r8d, r15d
0x18001a0b1  mov     [rsp+98h+var_60], rax
0x18001a0b6  sbb     rdx, rdx
0x18001a0b9  mov     eax, [rsp+98h+arg_28]
0x18001a0c0  and     rdx, rcx
0x18001a0c3  mov     [rsp+98h+var_68], eax
0x18001a0c7  mov     rcx, rbx
0x18001a0ca  mov     eax, [rsp+98h+arg_20]
0x18001a0d1  mov     [rsp+98h+var_70], eax
0x18001a0d5  mov     [rsp+98h+var_78], edi
0x18001a0d9  call    ?HrInit@CBitmapLock@@QEAAJPEAUIMILBitmap@@IIW4Enum@MilPixelFormat@@IIPEAUIBitmapMemory@@K@Z; CBitmapLock::HrInit(IMILBitmap *,uint,uint,MilPixelFormat::Enum,uint,uint,IBitmapMemory *,ulong)
0x18001a0de  mov     edi, eax
0x18001a0e0  test    eax, eax
0x18001a0e2  jns     short loc_18001A109
0x18001a0e4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001a0eb  jz      short loc_18001A105
0x18001a0ed  mov     ecx, eax; int
0x18001a0ef  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a0f4  mov     rax, [rbx]
0x18001a0f7  mov     rcx, rbx
0x18001a0fa  mov     rax, [rax+10h]
0x18001a0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a103  jmp     short loc_18001A14B
0x18001a105  test    eax, eax
0x18001a107  js      short loc_18001A0F4
0x18001a109  test    bpl, 2
0x18001a10d  jz      short loc_18001A11C
0x18001a10f  add     dword ptr [rsi+60h], 1
0x18001a113  jnz     short loc_18001A11C
0x18001a115  mov     dword ptr [rsi+60h], 1
0x18001a11c  lea     rax, [rbx+10h]
0x18001a120  neg     rbx
0x18001a123  sbb     rcx, rcx
0x18001a126  and     rcx, rax
0x18001a129  mov     rax, [rsp+98h+arg_40]
0x18001a131  mov     [rax], rcx
0x18001a134  jmp     short loc_18001A14B
0x18001a136  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001a13d  mov     edi, 8007000Eh
0x18001a142  jz      short loc_18001A14B
0x18001a144  mov     ecx, edi; int
0x18001a146  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001a14b  mov     eax, edi
0x18001a14d  add     rsp, 68h
0x18001a151  pop     r15
0x18001a153  pop     r14
0x18001a155  pop     rdi
0x18001a156  pop     rsi
0x18001a157  pop     rbp
0x18001a158  pop     rbx
0x18001a159  retn
```

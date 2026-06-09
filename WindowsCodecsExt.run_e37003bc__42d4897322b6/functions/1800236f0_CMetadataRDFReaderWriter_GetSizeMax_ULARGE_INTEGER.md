# CMetadataRDFReaderWriter::GetSizeMax(_ULARGE_INTEGER *)

- ea: `0x1800236f0`
- end: `0x18002383d`
- name: `?GetSizeMax@CMetadataRDFReaderWriter@@UEAAJPEAT_ULARGE_INTEGER@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x1800215e8`
- `0x180021a30`
- `0x180022348`
- `0x1800236f0`
- `0x180023f00`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::GetSizeMax(CMetadataRDFReaderWriter *this, union _ULARGE_INTEGER *a2)
{
  unsigned int v4; // ebx
  CSizeStream *v5; // rax
  CSizeStream *v6; // rax
  CSizeStream *v7; // rdi
  int v8; // eax
  char *v10; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v11[16]; // [rsp+30h] [rbp-78h] BYREF
  ULONGLONG v12; // [rsp+40h] [rbp-68h]

  v10 = (char *)this + 32;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 32));
  if ( !a2 )
  {
    v4 = -2147024809;
    goto LABEL_15;
  }
  v5 = (CSizeStream *)operator new(0x28u);
  if ( v5 )
  {
    v6 = CSizeStream::CSizeStream(v5);
    v7 = v6;
    if ( v6 )
    {
      (*(void (__fastcall **)(CSizeStream *))(*(_QWORD *)v6 + 8LL))(v6);
      memset_0(v11, 0, 0x50u);
      v8 = (*(__int64 (__fastcall **)(char *, _QWORD *, _QWORD))(*((_QWORD *)this - 1) + 240LL))(
             (char *)this - 8,
             (_QWORD *)v7 + 2,
             0);
      v4 = v8;
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD *, _BYTE *, __int64))(*((_QWORD *)v7 + 2) + 96LL))(
               (_QWORD *)v7 + 2,
               v11,
               1);
        v4 = v8;
        if ( v8 >= 0 )
        {
          a2->QuadPart = v12;
          goto LABEL_13;
        }
        if ( !g_doStackCaptures )
          goto LABEL_13;
      }
      else if ( !g_doStackCaptures )
      {
LABEL_13:
        (*(void (__fastcall **)(CSizeStream *))(*(_QWORD *)v7 + 16LL))(v7);
        goto LABEL_17;
      }
      DoStackCapture(v8);
      goto LABEL_13;
    }
  }
  v4 = -2147024882;
LABEL_15:
  if ( g_doStackCaptures )
    DoStackCapture(v4);
LABEL_17:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v10);
  return v4;
}

```

## disassembly

```asm
0x1800236f0  mov     [rsp+arg_10], rbx
0x1800236f5  push    rsi
0x1800236f6  push    rdi
0x1800236f7  push    r14
0x1800236f9  sub     rsp, 90h
0x180023700  mov     rax, cs:__security_cookie
0x180023707  xor     rax, rsp
0x18002370a  mov     [rsp+0A8h+var_28], rax
0x180023712  mov     rbx, rcx
0x180023715  mov     rsi, rdx
0x180023718  add     rcx, 20h ; ' '; this
0x18002371c  mov     [rsp+0A8h+var_88], rcx
0x180023721  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180023726  test    rsi, rsi
0x180023729  jnz     short loc_180023735
0x18002372b  mov     ebx, 80070057h
0x180023730  jmp     loc_1800237FD
0x180023735  mov     ecx, 28h ; '('; Size
0x18002373a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002373f  test    rax, rax
0x180023742  jz      loc_1800237F8
0x180023748  mov     rcx, rax; this
0x18002374b  call    ??0CSizeStream@@QEAA@XZ; CSizeStream::CSizeStream(void)
0x180023750  mov     rdi, rax
0x180023753  test    rax, rax
0x180023756  jz      loc_1800237F8
0x18002375c  mov     rax, [rax]
0x18002375f  mov     rcx, rdi
0x180023762  mov     rax, [rax+8]
0x180023766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002376b  xor     edx, edx; Val
0x18002376d  lea     rcx, [rsp+0A8h+var_78]; void *
0x180023772  lea     r8d, [rdx+50h]; Size
0x180023776  call    memset_0
0x18002377b  lea     rcx, [rbx-8]
0x18002377f  xor     r8d, r8d
0x180023782  mov     rax, [rcx]
0x180023785  lea     r14, [rdi+10h]
0x180023789  mov     rdx, r14
0x18002378c  mov     rax, [rax+0F0h]
0x180023793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023798  mov     ebx, eax
0x18002379a  test    eax, eax
0x18002379c  jns     short loc_1800237A9
0x18002379e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800237a5  jz      short loc_1800237E7
0x1800237a7  jmp     short loc_1800237D2
0x1800237a9  mov     rax, [r14]
0x1800237ac  lea     rdx, [rsp+0A8h+var_78]
0x1800237b1  mov     r8d, 1
0x1800237b7  mov     rcx, r14
0x1800237ba  mov     rax, [rax+60h]
0x1800237be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237c3  mov     ebx, eax
0x1800237c5  test    eax, eax
0x1800237c7  jns     short loc_1800237DF
0x1800237c9  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800237d0  jz      short loc_1800237DB
0x1800237d2  mov     ecx, eax; int
0x1800237d4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800237d9  jmp     short loc_1800237E7
0x1800237db  test    eax, eax
0x1800237dd  js      short loc_1800237E7
0x1800237df  mov     rax, [rsp+0A8h+var_68]
0x1800237e4  mov     [rsi], rax
0x1800237e7  mov     rax, [rdi]
0x1800237ea  mov     rcx, rdi
0x1800237ed  mov     rax, [rax+10h]
0x1800237f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f6  jmp     short loc_18002380D
0x1800237f8  mov     ebx, 8007000Eh
0x1800237fd  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180023804  jz      short loc_18002380D
0x180023806  mov     ecx, ebx; int
0x180023808  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002380d  lea     rcx, [rsp+0A8h+var_88]
0x180023812  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180023817  mov     eax, ebx
0x180023819  mov     rcx, [rsp+0A8h+var_28]
0x180023821  xor     rcx, rsp; StackCookie
0x180023824  call    __security_check_cookie
0x180023829  mov     rbx, [rsp+0A8h+arg_10]
0x180023831  add     rsp, 90h
0x180023838  pop     r14
0x18002383a  pop     rdi
0x18002383b  pop     rsi
0x18002383c  retn
```

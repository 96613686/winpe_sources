# CScope::Save(IStream *,int)

- ea: `0x18004da60`
- end: `0x18004dbf8`
- name: `?Save@CScope@@UEAAJPEAUIStream@@H@Z`
- size: `408`
- prototype: `int(CScope *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180047ae0`
- `0x18004da60`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x18004da94`
- `SHCORE!IStream_Write` at `0x18004dad2`
- `SHCORE!IStream_Write` at `0x18004db8c`
- `SHCORE!IStream_Write` at `0x18004dba5`
- `SHCORE!IStream_Write` at `0x18004da94`
- `SHCORE!IStream_Write` at `0x18004dad2`
- `SHCORE!IStream_Write` at `0x18004db8c`
- `SHCORE!IStream_Write` at `0x18004dba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004dbb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004dbb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004daab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004daab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004dbb9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004dbb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004dbd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004dbd2`

## pseudocode

```c
__int64 __fastcall CScope::Save(CScope *this, struct IStream *a2, int a3)
{
  HRESULT v6; // ebx
  int *v7; // rax
  int v8; // ecx
  _DWORD *v9; // r15
  int v10; // ebp
  __int64 (__fastcall ***Ptr)(PVOID, GUID *, _QWORD *); // rax
  _QWORD v13[7]; // [rsp+20h] [rbp-38h] BYREF
  int pv; // [rsp+78h] [rbp+20h] BYREF

  pv = -2147483646;
  v6 = IStream_Write(a2, &pv, 4u);
  if ( v6 >= 0 )
  {
    AcquireSRWLockShared((PSRWLOCK)this + 10);
    v7 = (int *)*((_QWORD *)this + 6);
    if ( v7 )
      v8 = *v7;
    else
      v8 = 0;
    pv = v8;
    v6 = IStream_Write(a2, &pv, 4u);
    if ( v6 >= 0 )
    {
      if ( !pv )
        goto LABEL_16;
      v9 = (_DWORD *)*((_QWORD *)this + 6);
      if ( v9 && (LODWORD(v9) = *v9, (int)v9 > 64) )
      {
        v6 = -2147418113;
      }
      else
      {
        v6 = 0;
        v10 = 0;
        do
        {
          if ( v10 >= (int)v9 )
            break;
          Ptr = (__int64 (__fastcall ***)(PVOID, GUID *, _QWORD *))g_pfn_DPA_GetPtr(*((HDPA *)this + 6), v10);
          v13[0] = 0;
          v6 = (**Ptr)(Ptr, &GUID_00000109_0000_0000_c000_000000000046, v13);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, __int64))(*(_QWORD *)v13[0] + 48LL))(
                   v13[0],
                   a2,
                   1);
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
          }
          ++v10;
        }
        while ( v6 >= 0 );
      }
      if ( v6 >= 0 )
      {
LABEL_16:
        v6 = IStream_Write(a2, (char *)this + 28, 0x10u);
        if ( v6 >= 0 )
          v6 = IStream_Write(a2, (char *)this + 44, 4u);
      }
    }
    ReleaseSRWLockShared((PSRWLOCK)this + 10);
    AcquireSRWLockExclusive((PSRWLOCK)this + 10);
    if ( v6 >= 0 && a3 )
      *((_DWORD *)this + 6) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 10);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004da60  mov     rax, rsp
0x18004da63  mov     [rax+8], rbx
0x18004da67  mov     [rax+10h], rbp
0x18004da6b  push    rsi
0x18004da6c  push    rdi
0x18004da6d  push    r12
0x18004da6f  push    r14
0x18004da71  push    r15
0x18004da73  sub     rsp, 30h
0x18004da77  mov     r14, rdx
0x18004da7a  mov     dword ptr [rax+20h], 80000002h
0x18004da81  mov     r12d, r8d
0x18004da84  lea     rdx, [rax+20h]; pv
0x18004da88  mov     rdi, rcx
0x18004da8b  mov     r8d, 4; cb
0x18004da91  mov     rcx, r14; pstm
0x18004da94  call    cs:__imp_IStream_Write
0x18004da9a  mov     ebx, eax
0x18004da9c  test    eax, eax
0x18004da9e  js      loc_18004DBD8
0x18004daa4  lea     rsi, [rdi+50h]
0x18004daa8  mov     rcx, rsi; SRWLock
0x18004daab  call    cs:__imp_AcquireSRWLockShared
0x18004dab1  mov     rax, [rdi+30h]
0x18004dab5  test    rax, rax
0x18004dab8  jnz     loc_18004DBF1
0x18004dabe  xor     ecx, ecx
0x18004dac0  mov     [rsp+58h+pv], ecx
0x18004dac4  lea     rdx, [rsp+58h+pv]; pv
0x18004dac9  mov     rcx, r14; pstm
0x18004dacc  mov     r8d, 4; cb
0x18004dad2  call    cs:__imp_IStream_Write
0x18004dad8  mov     ebx, eax
0x18004dada  test    eax, eax
0x18004dadc  js      loc_18004DBAD
0x18004dae2  cmp     [rsp+58h+pv], 0
0x18004dae7  jz      loc_18004DB7F
0x18004daed  mov     r15, [rdi+30h]
0x18004daf1  test    r15, r15
0x18004daf4  jz      short loc_18004DAFF
0x18004daf6  mov     r15d, [r15]
0x18004daf9  cmp     r15d, 40h ; '@'
0x18004dafd  jg      short loc_18004DB76
0x18004daff  xor     ebx, ebx
0x18004db01  xor     ebp, ebp
0x18004db03  cmp     ebp, r15d
0x18004db06  jge     short loc_18004DB7B
0x18004db08  mov     rcx, [rdi+30h]; hdpa
0x18004db0c  movsxd  rdx, ebp; i
0x18004db0f  call    cs:g_pfn_DPA_GetPtr
0x18004db15  lea     r8, [rsp+58h+var_38]
0x18004db1a  mov     [rsp+58h+var_38], 0
0x18004db23  mov     r9, rax
0x18004db26  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x18004db2d  mov     rcx, [rax]
0x18004db30  mov     rax, [rcx]
0x18004db33  mov     rcx, r9
0x18004db36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db3b  mov     ebx, eax
0x18004db3d  test    eax, eax
0x18004db3f  js      short loc_18004DB6E
0x18004db41  mov     rcx, [rsp+58h+var_38]
0x18004db46  mov     r8d, 1
0x18004db4c  mov     rdx, r14
0x18004db4f  mov     rax, [rcx]
0x18004db52  mov     rax, [rax+30h]
0x18004db56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db5b  mov     rcx, [rsp+58h+var_38]
0x18004db60  mov     ebx, eax
0x18004db62  mov     rax, [rcx]
0x18004db65  mov     rax, [rax+10h]
0x18004db69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004db6e  inc     ebp
0x18004db70  test    ebx, ebx
0x18004db72  jns     short loc_18004DB03
0x18004db74  jmp     short loc_18004DB7B
0x18004db76  mov     ebx, 8000FFFFh
0x18004db7b  test    ebx, ebx
0x18004db7d  js      short loc_18004DBAD
0x18004db7f  lea     rdx, [rdi+1Ch]; pv
0x18004db83  mov     r8d, 10h; cb
0x18004db89  mov     rcx, r14; pstm
0x18004db8c  call    cs:__imp_IStream_Write
0x18004db92  mov     ebx, eax
0x18004db94  test    eax, eax
0x18004db96  js      short loc_18004DBAD
0x18004db98  lea     rdx, [rdi+2Ch]; pv
0x18004db9c  mov     r8d, 4; cb
0x18004dba2  mov     rcx, r14; pstm
0x18004dba5  call    cs:__imp_IStream_Write
0x18004dbab  mov     ebx, eax
0x18004dbad  mov     rcx, rsi; SRWLock
0x18004dbb0  call    cs:__imp_ReleaseSRWLockShared
0x18004dbb6  mov     rcx, rsi; SRWLock
0x18004dbb9  call    cs:__imp_AcquireSRWLockExclusive
0x18004dbbf  test    ebx, ebx
0x18004dbc1  js      short loc_18004DBCF
0x18004dbc3  test    r12d, r12d
0x18004dbc6  jz      short loc_18004DBCF
0x18004dbc8  mov     dword ptr [rdi+18h], 0
0x18004dbcf  mov     rcx, rsi; SRWLock
0x18004dbd2  call    cs:__imp_ReleaseSRWLockExclusive
0x18004dbd8  mov     rbp, [rsp+58h+arg_8]
0x18004dbdd  mov     eax, ebx
0x18004dbdf  mov     rbx, [rsp+58h+arg_0]
0x18004dbe4  add     rsp, 30h
0x18004dbe8  pop     r15
0x18004dbea  pop     r14
0x18004dbec  pop     r12
0x18004dbee  pop     rdi
0x18004dbef  pop     rsi
0x18004dbf0  retn
0x18004dbf1  mov     ecx, [rax]
0x18004dbf3  jmp     loc_18004DAC0
```

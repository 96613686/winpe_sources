# CMPEG2Demultiplexer::ReadFromStream(IStream *)

- ea: `0x180016ae0`
- end: `0x180016c85`
- name: `?ReadFromStream@CMPEG2Demultiplexer@@UEAAJPEAUIStream@@@Z`
- size: `421`
- prototype: `int(CMPEG2Demultiplexer *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180016ae0`
- `0x1800170b4`
- `0x180017234`
- `0x180017340`
- `0x1800176e8`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180016c63`
- `KERNEL32!LeaveCriticalSection` at `0x180016c6c`
- `KERNEL32!LeaveCriticalSection` at `0x180016c63`
- `KERNEL32!LeaveCriticalSection` at `0x180016c6c`
- `KERNEL32!EnterCriticalSection` at `0x180016b21`
- `KERNEL32!EnterCriticalSection` at `0x180016b2b`
- `KERNEL32!EnterCriticalSection` at `0x180016b21`
- `KERNEL32!EnterCriticalSection` at `0x180016b2b`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::ReadFromStream(LPCRITICAL_SECTION *this, struct IStream *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  int v5; // ebx
  int v6; // r14d
  CMPEG2Demultiplexer *v7; // rcx
  volatile signed __int32 *v8; // rdi
  int v9; // eax
  struct DEMUX_PIN_RECORD *v11; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v12; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v13; // [rsp+98h] [rbp+50h] BYREF
  int v14; // [rsp+A0h] [rbp+58h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 22);
  v12 = 0;
  v13 = 0;
  v11 = 0;
  v14 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 22));
  EnterCriticalSection(*(this - 5));
  v5 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Read)(a2, &v14, 4);
  if ( v5 >= 0 && !v14 )
  {
    v5 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, _QWORD))a2->lpVtbl->Read)(a2, &v12, 4, 0);
    if ( v5 >= 0 )
    {
      v5 = CMPEG2Demultiplexer::SetStreamType((CMPEG2Demultiplexer *)(this - 15), v12);
      if ( v5 >= 0 )
      {
        v5 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, _QWORD))a2->lpVtbl->Read)(
               a2,
               &v13,
               4,
               0);
        if ( v5 >= 0 )
        {
          v6 = 0;
          if ( v13 )
          {
            while ( 1 )
            {
              if ( v5 < 0 )
                goto LABEL_18;
              v5 = CMPEG2Demultiplexer::RestoreOutputPin_((CMPEG2Demultiplexer *)(this - 15), a2, &v11);
              if ( v5 >= 0 )
                break;
LABEL_17:
              if ( ++v6 >= v13 )
                goto LABEL_18;
            }
            v8 = (volatile signed __int32 *)v11;
            if ( v12 == 1 )
            {
              v9 = CMPEG2Demultiplexer::RestorePinPIDMaps_(v7, a2, v11);
            }
            else
            {
              if ( v12 != 2 )
              {
LABEL_14:
                if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 && v8 )
                {
                  operator delete(*((void **)v8 + 2));
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)v8 + 8LL) + 16LL))(*(_QWORD *)(*(_QWORD *)v8 + 8LL));
                  operator delete((void *)v8);
                }
                goto LABEL_17;
              }
              v9 = CMPEG2Demultiplexer::RestorePinStreamIdMaps_(v7, a2, v11);
            }
            v5 = v9;
            goto LABEL_14;
          }
        }
      }
    }
  }
LABEL_18:
  LeaveCriticalSection(*(this - 5));
  LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016ae0  push    rbp
0x180016ae2  push    rbx
0x180016ae3  push    rsi
0x180016ae4  push    rdi
0x180016ae5  push    r12
0x180016ae7  push    r13
0x180016ae9  push    r14
0x180016aeb  push    r15
0x180016aed  mov     rbp, rsp
0x180016af0  sub     rsp, 48h
0x180016af4  lea     r12, [rcx+0B0h]
0x180016afb  mov     [rbp+arg_0], 0
0x180016b02  mov     r13, rcx
0x180016b05  mov     [rbp+arg_8], 0
0x180016b0c  mov     rcx, r12; lpCriticalSection
0x180016b0f  mov     [rbp+var_18], 0
0x180016b17  mov     rsi, rdx
0x180016b1a  mov     [rbp+arg_10], 0
0x180016b21  call    cs:__imp_EnterCriticalSection
0x180016b27  mov     rcx, [r13-28h]; lpCriticalSection
0x180016b2b  call    cs:__imp_EnterCriticalSection
0x180016b31  mov     rax, [rsi]
0x180016b34  lea     rdx, [rbp+arg_10]
0x180016b38  xor     r9d, r9d
0x180016b3b  mov     rcx, rsi
0x180016b3e  mov     rax, [rax+18h]
0x180016b42  lea     edi, [r9+4]
0x180016b46  mov     r8d, edi
0x180016b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b4e  mov     ebx, eax
0x180016b50  test    eax, eax
0x180016b52  js      loc_180016C5F
0x180016b58  cmp     [rbp+arg_10], 0
0x180016b5c  jnz     loc_180016C5F
0x180016b62  mov     rax, [rsi]
0x180016b65  lea     rdx, [rbp+arg_0]
0x180016b69  xor     r9d, r9d
0x180016b6c  mov     r8d, edi
0x180016b6f  mov     rcx, rsi
0x180016b72  mov     rax, [rax+18h]
0x180016b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b7b  mov     ebx, eax
0x180016b7d  test    eax, eax
0x180016b7f  js      loc_180016C5F
0x180016b85  mov     edx, [rbp+arg_0]; unsigned int
0x180016b88  lea     rcx, [r13-78h]; this
0x180016b8c  call    ?SetStreamType@CMPEG2Demultiplexer@@QEAAJK@Z; CMPEG2Demultiplexer::SetStreamType(ulong)
0x180016b91  mov     ebx, eax
0x180016b93  test    eax, eax
0x180016b95  js      loc_180016C5F
0x180016b9b  mov     rax, [rsi]
0x180016b9e  lea     rdx, [rbp+arg_8]
0x180016ba2  xor     r9d, r9d
0x180016ba5  mov     r8d, edi
0x180016ba8  mov     rcx, rsi
0x180016bab  mov     rax, [rax+18h]
0x180016baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bb4  mov     ebx, eax
0x180016bb6  test    eax, eax
0x180016bb8  js      loc_180016C5F
0x180016bbe  xor     r14d, r14d
0x180016bc1  cmp     [rbp+arg_8], r14d
0x180016bc5  jbe     loc_180016C5F
0x180016bcb  test    ebx, ebx
0x180016bcd  js      loc_180016C5F
0x180016bd3  lea     r8, [rbp+var_18]; struct DEMUX_PIN_RECORD **
0x180016bd7  mov     rdx, rsi; struct IStream *
0x180016bda  lea     rcx, [r13-78h]; this
0x180016bde  call    ?RestoreOutputPin_@CMPEG2Demultiplexer@@AEAAJPEAUIStream@@PEAPEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::RestoreOutputPin_(IStream *,DEMUX_PIN_RECORD * *)
0x180016be3  mov     ebx, eax
0x180016be5  test    eax, eax
0x180016be7  js      short loc_180016C52
0x180016be9  mov     eax, [rbp+arg_0]
0x180016bec  mov     rdi, [rbp+var_18]
0x180016bf0  sub     eax, 1
0x180016bf3  jz      short loc_180016C07
0x180016bf5  cmp     eax, 1
0x180016bf8  jnz     short loc_180016C14
0x180016bfa  mov     r8, rdi; struct DEMUX_PIN_RECORD *
0x180016bfd  mov     rdx, rsi; struct IStream *
0x180016c00  call    ?RestorePinStreamIdMaps_@CMPEG2Demultiplexer@@AEAAJPEAUIStream@@PEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::RestorePinStreamIdMaps_(IStream *,DEMUX_PIN_RECORD *)
0x180016c05  jmp     short loc_180016C12
0x180016c07  mov     r8, rdi; struct DEMUX_PIN_RECORD *
0x180016c0a  mov     rdx, rsi; struct IStream *
0x180016c0d  call    ?RestorePinPIDMaps_@CMPEG2Demultiplexer@@AEAAJPEAUIStream@@PEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::RestorePinPIDMaps_(IStream *,DEMUX_PIN_RECORD *)
0x180016c12  mov     ebx, eax
0x180016c14  or      eax, 0FFFFFFFFh
0x180016c17  lock xadd [rdi+8], eax
0x180016c1c  cmp     eax, 1
0x180016c1f  jnz     short loc_180016C52
0x180016c21  test    rdi, rdi
0x180016c24  jz      short loc_180016C52
0x180016c26  mov     rcx, [rdi+10h]; void *
0x180016c2a  lea     edx, [rax+1]; unsigned __int64
0x180016c2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016c32  mov     rax, [rdi]
0x180016c35  mov     rcx, [rax+8]
0x180016c39  mov     rax, [rcx]
0x180016c3c  mov     rax, [rax+10h]
0x180016c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c45  mov     edx, 18h; unsigned __int64
0x180016c4a  mov     rcx, rdi; void *
0x180016c4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016c52  inc     r14d
0x180016c55  cmp     r14d, [rbp+arg_8]
0x180016c59  jb      loc_180016BCB
0x180016c5f  mov     rcx, [r13-28h]; lpCriticalSection
0x180016c63  call    cs:__imp_LeaveCriticalSection
0x180016c69  mov     rcx, r12; lpCriticalSection
0x180016c6c  call    cs:__imp_LeaveCriticalSection
0x180016c72  mov     eax, ebx
0x180016c74  add     rsp, 48h
0x180016c78  pop     r15
0x180016c7a  pop     r14
0x180016c7c  pop     r13
0x180016c7e  pop     r12
0x180016c80  pop     rdi
0x180016c81  pop     rsi
0x180016c82  pop     rbx
0x180016c83  pop     rbp
0x180016c84  retn
```

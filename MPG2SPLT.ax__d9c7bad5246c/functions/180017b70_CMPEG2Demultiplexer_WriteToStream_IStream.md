# CMPEG2Demultiplexer::WriteToStream(IStream *)

- ea: `0x180017b70`
- end: `0x180017cf1`
- name: `?WriteToStream@CMPEG2Demultiplexer@@UEAAJPEAUIStream@@@Z`
- size: `385`
- prototype: `int(CMPEG2Demultiplexer *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180016410`
- `0x1800165f0`
- `0x180016758`
- `0x180017b70`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180017cd1`
- `KERNEL32!LeaveCriticalSection` at `0x180017cda`
- `KERNEL32!LeaveCriticalSection` at `0x180017cd1`
- `KERNEL32!LeaveCriticalSection` at `0x180017cda`
- `KERNEL32!EnterCriticalSection` at `0x180017ba7`
- `KERNEL32!EnterCriticalSection` at `0x180017bb1`
- `KERNEL32!EnterCriticalSection` at `0x180017ba7`
- `KERNEL32!EnterCriticalSection` at `0x180017bb1`

## pseudocode

```c
__int64 __fastcall CMPEG2Demultiplexer::WriteToStream(CMPEG2Demultiplexer *this, struct IStream *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r12
  __int64 v5; // rax
  int v6; // ecx
  struct IStreamVtbl *lpVtbl; // rax
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  int v11; // ecx
  struct IStreamVtbl *v12; // rax
  __int64 i; // rsi
  struct DEMUX_PIN_RECORD *v14; // r14
  __int64 v15; // rcx
  CMPEG2Demultiplexer *v16; // rcx
  int v17; // eax
  unsigned int v19; // [rsp+70h] [rbp+40h] BYREF
  int v20; // [rsp+78h] [rbp+48h] BYREF
  int v21; // [rsp+80h] [rbp+50h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  v19 = 0;
  v21 = 0;
  v20 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this - 5));
  v5 = *((_QWORD *)this + 27);
  if ( v5 )
    v6 = *(_DWORD *)(v5 + 176);
  else
    v6 = 0;
  lpVtbl = a2->lpVtbl;
  v20 = v6;
  v8 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))lpVtbl->Write)(a2, &v20, 4);
  v9 = v8;
  if ( !v20 && v8 >= 0 )
  {
    v10 = *((_QWORD *)this + 27);
    v11 = v10 ? *(_DWORD *)(v10 + 128) : 0;
    v12 = a2->lpVtbl;
    v21 = v11;
    v9 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64, _QWORD))v12->Write)(a2, &v21, 4, 0);
    if ( v9 >= 0 )
    {
      v19 = *((_DWORD *)this + 18);
      v9 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, _QWORD))a2->lpVtbl->Write)(
             a2,
             &v19,
             4,
             0);
      if ( v9 >= 0 )
      {
        for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
        {
          if ( v9 < 0 )
            break;
          if ( (unsigned int)i < *((_DWORD *)this + 18) )
          {
            v15 = 0;
            v14 = *(struct DEMUX_PIN_RECORD **)(*((_QWORD *)this + 8) + 8 * i);
          }
          else
          {
            v14 = 0;
            v15 = 2147942487LL;
          }
          if ( (int)v15 < 0 )
            v14 = 0;
          v9 = CMPEG2Demultiplexer::PersistOutputPin_((CMPEG2Demultiplexer *)v15, a2, v14);
          if ( v9 >= 0 )
          {
            if ( v21 == 1 )
            {
              v17 = CMPEG2Demultiplexer::PersistPinPIDMaps_(v16, a2, v14);
              goto LABEL_23;
            }
            if ( v21 == 2 )
            {
              v17 = CMPEG2Demultiplexer::PersistPinStreamIdMaps_(v16, a2, v14);
LABEL_23:
              v9 = v17;
            }
          }
        }
      }
    }
  }
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this - 5));
  LeaveCriticalSection(v2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180017b70  push    rbp
0x180017b72  push    rbx
0x180017b73  push    rsi
0x180017b74  push    rdi
0x180017b75  push    r12
0x180017b77  push    r14
0x180017b79  push    r15
0x180017b7b  mov     rbp, rsp
0x180017b7e  sub     rsp, 30h
0x180017b82  lea     r12, [rcx+0B0h]
0x180017b89  mov     [rbp+arg_0], 0
0x180017b90  mov     rdi, rcx
0x180017b93  mov     [rbp+arg_10], 0
0x180017b9a  mov     rcx, r12; lpCriticalSection
0x180017b9d  mov     [rbp+arg_8], 0
0x180017ba4  mov     r15, rdx
0x180017ba7  call    cs:__imp_EnterCriticalSection
0x180017bad  mov     rcx, [rdi-28h]; lpCriticalSection
0x180017bb1  call    cs:__imp_EnterCriticalSection
0x180017bb7  mov     rax, [rdi+0D8h]
0x180017bbe  test    rax, rax
0x180017bc1  jz      short loc_180017BCB
0x180017bc3  mov     ecx, [rax+0B0h]
0x180017bc9  jmp     short loc_180017BCD
0x180017bcb  xor     ecx, ecx
0x180017bcd  mov     rax, [r15]
0x180017bd0  lea     rdx, [rbp+arg_8]
0x180017bd4  xor     r9d, r9d
0x180017bd7  mov     [rbp+arg_8], ecx
0x180017bda  mov     rcx, r15
0x180017bdd  mov     rax, [rax+20h]
0x180017be1  lea     esi, [r9+4]
0x180017be5  mov     r8d, esi
0x180017be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bed  cmp     [rbp+arg_8], 0
0x180017bf1  mov     ebx, eax
0x180017bf3  jnz     loc_180017CCD
0x180017bf9  test    eax, eax
0x180017bfb  js      loc_180017CCD
0x180017c01  mov     rax, [rdi+0D8h]
0x180017c08  test    rax, rax
0x180017c0b  jz      short loc_180017C15
0x180017c0d  mov     ecx, [rax+80h]
0x180017c13  jmp     short loc_180017C17
0x180017c15  xor     ecx, ecx
0x180017c17  mov     rax, [r15]
0x180017c1a  lea     rdx, [rbp+arg_10]
0x180017c1e  mov     [rbp+arg_10], ecx
0x180017c21  xor     r9d, r9d
0x180017c24  mov     r8d, esi
0x180017c27  mov     rcx, r15
0x180017c2a  mov     rax, [rax+20h]
0x180017c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c33  mov     ebx, eax
0x180017c35  test    eax, eax
0x180017c37  js      loc_180017CCD
0x180017c3d  mov     eax, [rdi+48h]
0x180017c40  lea     rdx, [rbp+arg_0]
0x180017c44  mov     [rbp+arg_0], eax
0x180017c47  xor     r9d, r9d
0x180017c4a  mov     rax, [r15]
0x180017c4d  mov     r8d, esi
0x180017c50  mov     rcx, r15
0x180017c53  mov     rax, [rax+20h]
0x180017c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c5c  mov     ebx, eax
0x180017c5e  test    eax, eax
0x180017c60  js      short loc_180017CCD
0x180017c62  xor     esi, esi
0x180017c64  cmp     [rbp+arg_0], esi
0x180017c67  jbe     short loc_180017CCD
0x180017c69  test    ebx, ebx
0x180017c6b  js      short loc_180017CCD
0x180017c6d  cmp     esi, [rdi+48h]
0x180017c70  jb      short loc_180017C7C
0x180017c72  xor     r14d, r14d
0x180017c75  mov     ecx, 80070057h
0x180017c7a  jmp     short loc_180017C86
0x180017c7c  mov     rax, [rdi+40h]
0x180017c80  xor     ecx, ecx; this
0x180017c82  mov     r14, [rax+rsi*8]
0x180017c86  xor     eax, eax
0x180017c88  mov     rdx, r15; struct IStream *
0x180017c8b  test    ecx, ecx
0x180017c8d  cmovs   r14, rax
0x180017c91  mov     r8, r14; struct DEMUX_PIN_RECORD *
0x180017c94  call    ?PersistOutputPin_@CMPEG2Demultiplexer@@AEAAJPEAUIStream@@PEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::PersistOutputPin_(IStream *,DEMUX_PIN_RECORD *)
0x180017c99  mov     ebx, eax
0x180017c9b  test    eax, eax
0x180017c9d  js      short loc_180017CC6
0x180017c9f  mov     eax, [rbp+arg_10]
0x180017ca2  sub     eax, 1
0x180017ca5  jz      short loc_180017CB9
0x180017ca7  cmp     eax, 1
0x180017caa  jnz     short loc_180017CC6
0x180017cac  mov     r8, r14; struct DEMUX_PIN_RECORD *
0x180017caf  mov     rdx, r15; struct IStream *
0x180017cb2  call    ?PersistPinStreamIdMaps_@CMPEG2Demultiplexer@@AEAAJPEAUIStream@@PEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::PersistPinStreamIdMaps_(IStream *,DEMUX_PIN_RECORD *)
0x180017cb7  jmp     short loc_180017CC4
0x180017cb9  mov     r8, r14; struct DEMUX_PIN_RECORD *
0x180017cbc  mov     rdx, r15; struct IStream *
0x180017cbf  call    ?PersistPinPIDMaps_@CMPEG2Demultiplexer@@AEAAJPEAUIStream@@PEAUDEMUX_PIN_RECORD@@@Z; CMPEG2Demultiplexer::PersistPinPIDMaps_(IStream *,DEMUX_PIN_RECORD *)
0x180017cc4  mov     ebx, eax
0x180017cc6  inc     esi
0x180017cc8  cmp     esi, [rbp+arg_0]
0x180017ccb  jb      short loc_180017C69
0x180017ccd  mov     rcx, [rdi-28h]; lpCriticalSection
0x180017cd1  call    cs:__imp_LeaveCriticalSection
0x180017cd7  mov     rcx, r12; lpCriticalSection
0x180017cda  call    cs:__imp_LeaveCriticalSection
0x180017ce0  mov     eax, ebx
0x180017ce2  add     rsp, 30h
0x180017ce6  pop     r15
0x180017ce8  pop     r14
0x180017cea  pop     r12
0x180017cec  pop     rdi
0x180017ced  pop     rsi
0x180017cee  pop     rbx
0x180017cef  pop     rbp
0x180017cf0  retn
```

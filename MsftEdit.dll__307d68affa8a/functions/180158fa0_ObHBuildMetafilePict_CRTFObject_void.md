# ObHBuildMetafilePict(CRTFObject *,void * &)

- ea: `0x180158fa0`
- end: `0x18015906c`
- name: `?ObHBuildMetafilePict@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z`
- size: `204`
- prototype: `void *__fastcall(struct CRTFObject *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800693d4`
- `0x180158fa0`
- `0x180205240`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180158fb7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180158fb7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180159017`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180159027`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180159050`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180159017`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180159027`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180159050`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158fcc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158fef`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158fcc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180158fef`
- `ext-ms-win-gdi-metafile-l1-1-0!SetMetaFileBitsEx` at `0x18015900a`
- `ext-ms-win-gdi-metafile-l1-1-0!SetMetaFileBitsEx` at `0x18015900a`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180159047`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x180159047`

## pseudocode

```c
void *__fastcall ObHBuildMetafilePict(struct CRTFObject *a1, void **a2)
{
  HGLOBAL v4; // rax
  void *v5; // rbx
  _DWORD *v6; // rax
  _DWORD *v7; // rdi
  const BYTE *v8; // rbp
  UINT v9; // eax
  HMETAFILE v10; // rcx

  v4 = GlobalAlloc(0x42u, 0x18u);
  v5 = v4;
  if ( v4 )
  {
    v6 = GlobalLock(v4);
    v7 = v6;
    if ( v6 )
    {
      *v6 = *((__int16 *)a1 + 1);
      v6[1] = *((_DWORD *)a1 + 5);
      v6[2] = *((_DWORD *)a1 + 6);
      v8 = (const BYTE *)GlobalLock(*a2);
      if ( v8 )
      {
        v9 = CW32System::GlobalSize(*a2);
        *((_QWORD *)v7 + 2) = SetMetaFileBitsEx(v9, v8);
        GlobalUnlock(*a2);
        if ( *((_QWORD *)v7 + 2) )
        {
          GlobalUnlock(v5);
          CW32System::GlobalFree(*a2);
          *a2 = 0;
          return v5;
        }
      }
      v10 = (HMETAFILE)*((_QWORD *)v7 + 2);
      if ( v10 )
        DeleteMetaFile(v10);
      GlobalUnlock(v5);
    }
    CW32System::GlobalFree(v5);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180158fa0  push    rbx
0x180158fa2  push    rbp
0x180158fa3  push    rsi
0x180158fa4  push    rdi
0x180158fa5  sub     rsp, 28h
0x180158fa9  mov     rsi, rdx
0x180158fac  mov     rbp, rcx
0x180158faf  mov     edx, 18h; dwBytes
0x180158fb4  lea     ecx, [rdx+2Ah]; uFlags
0x180158fb7  call    cs:__imp_GlobalAlloc
0x180158fbd  mov     rbx, rax
0x180158fc0  test    rax, rax
0x180158fc3  jz      loc_180159060
0x180158fc9  mov     rcx, rax; hMem
0x180158fcc  call    cs:__imp_GlobalLock
0x180158fd2  mov     rdi, rax
0x180158fd5  test    rax, rax
0x180158fd8  jz      short loc_180159056
0x180158fda  movsx   ecx, word ptr [rbp+2]
0x180158fde  mov     [rax], ecx
0x180158fe0  mov     ecx, [rbp+14h]
0x180158fe3  mov     [rax+4], ecx
0x180158fe6  mov     ecx, [rbp+18h]
0x180158fe9  mov     [rax+8], ecx
0x180158fec  mov     rcx, [rsi]; hMem
0x180158fef  call    cs:__imp_GlobalLock
0x180158ff5  mov     rbp, rax
0x180158ff8  test    rax, rax
0x180158ffb  jz      short loc_18015903E
0x180158ffd  mov     rcx, [rsi]; void *
0x180159000  call    ?GlobalSize@CW32System@@SAKPEAX@Z; CW32System::GlobalSize(void *)
0x180159005  mov     rdx, rbp; lpData
0x180159008  mov     ecx, eax; cbBuffer
0x18015900a  call    cs:__imp_SetMetaFileBitsEx
0x180159010  mov     [rdi+10h], rax
0x180159014  mov     rcx, [rsi]; hMem
0x180159017  call    cs:__imp_GlobalUnlock
0x18015901d  cmp     qword ptr [rdi+10h], 0
0x180159022  jz      short loc_18015903E
0x180159024  mov     rcx, rbx; hMem
0x180159027  call    cs:__imp_GlobalUnlock
0x18015902d  mov     rcx, [rsi]; void *
0x180159030  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180159035  mov     qword ptr [rsi], 0
0x18015903c  jmp     short loc_180159060
0x18015903e  mov     rcx, [rdi+10h]; hmf
0x180159042  test    rcx, rcx
0x180159045  jz      short loc_18015904D
0x180159047  call    cs:__imp_DeleteMetaFile
0x18015904d  mov     rcx, rbx; hMem
0x180159050  call    cs:__imp_GlobalUnlock
0x180159056  mov     rcx, rbx; void *
0x180159059  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18015905e  xor     ebx, ebx
0x180159060  mov     rax, rbx
0x180159063  add     rsp, 28h
0x180159067  pop     rdi
0x180159068  pop     rsi
0x180159069  pop     rbp
0x18015906a  pop     rbx
0x18015906b  retn
```

# CMetadataRDFReaderWriter::IsDirty(void)

- ea: `0x18001f370`
- end: `0x18001f430`
- name: `?IsDirty@CMetadataRDFReaderWriter@@UEAAJXZ`
- size: `192`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x18001f370`
- `0x18001f438`
- `0x180033010`

## pseudocode

```c
_BOOL8 __fastcall CMetadataRDFReaderWriter::IsDirty(CMetadataRDFReaderWriter *this)
{
  int v2; // eax
  unsigned int v3; // r15d
  __int64 i; // rdi
  RDFItem *v5; // rbp
  int v6; // eax
  BOOL v7; // ebx
  int v9; // [rsp+50h] [rbp+8h] BYREF
  char *v10; // [rsp+58h] [rbp+10h] BYREF

  v10 = (char *)this + 32;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 32));
  v2 = *((_DWORD *)this + 22);
  v9 = v2;
  if ( !v2 )
  {
    v3 = *((_DWORD *)this + 56);
    for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
    {
      v5 = *(RDFItem **)(*((_QWORD *)this + 25) + 8 * i);
      v6 = RDFItem::CheckHasChanged(v5, &v9);
      v7 = v6;
      if ( v6 < 0 )
      {
        if ( g_doStackCaptures )
          DoStackCapture(v6);
        goto LABEL_12;
      }
      v2 = v9;
      if ( v9 )
      {
        *((_DWORD *)v5 + 2) |= 1u;
        (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 1) + 128LL))((char *)this - 8, 1);
        v2 = 1;
        break;
      }
    }
  }
  v7 = v2 == 0;
LABEL_12:
  CGuard<CMTALock>::~CGuard<CMTALock>(&v10);
  return v7;
}

```

## disassembly

```asm
0x18001f370  mov     [rsp+arg_10], rbx
0x18001f375  push    rbp
0x18001f376  push    rsi
0x18001f377  push    rdi
0x18001f378  push    r14
0x18001f37a  push    r15
0x18001f37c  sub     rsp, 20h
0x18001f380  mov     rsi, rcx
0x18001f383  add     rcx, 20h ; ' '; this
0x18001f387  mov     [rsp+48h+arg_8], rcx
0x18001f38c  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18001f391  mov     eax, [rsi+58h]
0x18001f394  mov     [rsp+48h+arg_0], eax
0x18001f398  test    eax, eax
0x18001f39a  jnz     short loc_18001F40C
0x18001f39c  mov     r15d, [rsi+0E0h]
0x18001f3a3  xor     edi, edi
0x18001f3a5  cmp     edi, r15d
0x18001f3a8  jnb     short loc_18001F40C
0x18001f3aa  mov     rax, [rsi+0C8h]
0x18001f3b1  lea     rdx, [rsp+48h+arg_0]; int *
0x18001f3b6  mov     rbp, [rax+rdi*8]
0x18001f3ba  mov     rcx, rbp; this
0x18001f3bd  call    ?CheckHasChanged@RDFItem@@QEAAJPEAH@Z; RDFItem::CheckHasChanged(int *)
0x18001f3c2  mov     ebx, eax
0x18001f3c4  test    eax, eax
0x18001f3c6  jns     short loc_18001F3D5
0x18001f3c8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001f3cf  jnz     short loc_18001F3E1
0x18001f3d1  test    eax, eax
0x18001f3d3  js      short loc_18001F413
0x18001f3d5  mov     eax, [rsp+48h+arg_0]
0x18001f3d9  test    eax, eax
0x18001f3db  jnz     short loc_18001F3EA
0x18001f3dd  inc     edi
0x18001f3df  jmp     short loc_18001F3A5
0x18001f3e1  mov     ecx, eax; int
0x18001f3e3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001f3e8  jmp     short loc_18001F413
0x18001f3ea  or      dword ptr [rbp+8], 1
0x18001f3ee  lea     rcx, [rsi-8]
0x18001f3f2  mov     rax, [rsi-8]
0x18001f3f6  mov     edx, 1
0x18001f3fb  mov     rax, [rax+80h]
0x18001f402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f407  mov     eax, 1
0x18001f40c  xor     ebx, ebx
0x18001f40e  test    eax, eax
0x18001f410  setz    bl
0x18001f413  lea     rcx, [rsp+48h+arg_8]
0x18001f418  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18001f41d  mov     eax, ebx
0x18001f41f  mov     rbx, [rsp+48h+arg_10]
0x18001f424  add     rsp, 20h
0x18001f428  pop     r15
0x18001f42a  pop     r14
0x18001f42c  pop     rdi
0x18001f42d  pop     rsi
0x18001f42e  pop     rbp
0x18001f42f  retn
```

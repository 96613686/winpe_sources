# CFileStream::CommitAndWait(void)

- ea: `0x180016498`
- end: `0x180016509`
- name: `?CommitAndWait@CFileStream@@QEAAHXZ`
- size: `113`
- prototype: `__int64 __fastcall(CFileStream *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800067a0`
- `0x180009750`
- `0x18000b87c`
- `0x18001637c`

## callees

- `0x1800163d4`
- `0x180016498`
- `0x180016f00`

## pseudocode

```c
__int64 __fastcall CFileStream::CommitAndWait(CFileStream *this)
{
  int v2; // edi

  if ( (unsigned int)CFileBuffer::Commit((HANDLE *)this + 11 * *((int *)this + 91) + 1) )
  {
    v2 = 0;
    if ( *((int *)this + 90) <= 0 )
      return 1;
    while ( (unsigned int)CFileBuffer::WaitComplete((CFileStream *)((char *)this + 88 * v2 + 8)) )
    {
      if ( ++v2 >= *((_DWORD *)this + 90) )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016498  mov     [rsp+arg_0], rbx
0x18001649d  mov     [rsp+arg_8], rsi
0x1800164a2  push    rdi
0x1800164a3  sub     rsp, 20h
0x1800164a7  movsxd  rax, dword ptr [rcx+16Ch]
0x1800164ae  mov     rbx, rcx
0x1800164b1  imul    rdx, rax, 58h ; 'X'
0x1800164b5  add     rcx, 8
0x1800164b9  add     rcx, rdx; this
0x1800164bc  call    ?Commit@CFileBuffer@@QEAAHXZ; CFileBuffer::Commit(void)
0x1800164c1  test    eax, eax
0x1800164c3  jz      short loc_1800164F7
0x1800164c5  xor     edi, edi
0x1800164c7  cmp     [rbx+168h], edi
0x1800164cd  jle     short loc_1800164F0
0x1800164cf  lea     rsi, [rbx+8]
0x1800164d3  movsxd  rcx, edi
0x1800164d6  imul    rcx, 58h ; 'X'
0x1800164da  add     rcx, rsi; this
0x1800164dd  call    ?WaitComplete@CFileBuffer@@QEAAHXZ; CFileBuffer::WaitComplete(void)
0x1800164e2  test    eax, eax
0x1800164e4  jz      short loc_1800164F7
0x1800164e6  inc     edi
0x1800164e8  cmp     edi, [rbx+168h]
0x1800164ee  jl      short loc_1800164D3
0x1800164f0  mov     eax, 1
0x1800164f5  jmp     short loc_1800164F9
0x1800164f7  xor     eax, eax
0x1800164f9  mov     rbx, [rsp+28h+arg_0]
0x1800164fe  mov     rsi, [rsp+28h+arg_8]
0x180016503  add     rsp, 20h
0x180016507  pop     rdi
0x180016508  retn
```

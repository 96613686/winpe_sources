# write_text_utf16le_nolock(int,char const * const,uint)

- ea: `0x140021470`
- end: `0x14002158b`
- name: `?write_text_utf16le_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400218b8`

## callees

- `0x14000a640`
- `0x140021470`
- `0x140025090`

## import_xrefs

- `KERNEL32!WriteFile` at `0x14002153c`
- `KERNEL32!WriteFile` at `0x14002153c`
- `KERNEL32!GetLastError` at `0x140021558`
- `KERNEL32!GetLastError` at `0x140021558`

## pseudocode

```c
__int64 __fastcall write_text_utf16le_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  __int16 *v6; // rsi
  void *v7; // r14
  char *v8; // rbx
  __int16 v9; // ax
  DWORD v10; // ebx
  DWORD v11; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-1438h] BYREF
  _BYTE Buffer[5118]; // [rsp+40h] [rbp-1428h] BYREF
  __int16 v15; // [rsp+143Eh] [rbp-2Ah] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = a3;
  v7 = *(void **)(qword_14003E600[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
    while ( 1 )
    {
      v8 = Buffer;
      do
      {
        if ( (unsigned __int64)v6 >= v5 )
          break;
        v9 = *v6++;
        if ( v9 == 10 )
        {
          *(_DWORD *)(a1 + 8) += 2;
          *(_WORD *)v8 = 13;
          v8 += 2;
        }
        *(_WORD *)v8 = v9;
        v8 += 2;
      }
      while ( v8 < (char *)&v15 );
      NumberOfBytesWritten = 0;
      v10 = 2 * ((v8 - Buffer) >> 1);
      if ( !WriteFile(v7, Buffer, v10, &NumberOfBytesWritten, 0) )
        break;
      v11 = NumberOfBytesWritten;
      *(_DWORD *)(a1 + 4) += NumberOfBytesWritten;
      if ( v11 < v10 || (unsigned __int64)v6 >= v5 )
        return a1;
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x140021470  mov     [rsp+arg_0], rbx
0x140021475  mov     [rsp+arg_10], rbp
0x14002147a  push    rsi
0x14002147b  push    rdi
0x14002147c  push    r14
0x14002147e  mov     eax, 1450h
0x140021483  call    __alloca_probe
0x140021488  sub     rsp, rax
0x14002148b  mov     rax, cs:__security_cookie
0x140021492  xor     rax, rsp
0x140021495  mov     [rsp+1468h+var_28], rax
0x14002149d  movsxd  r10, edx
0x1400214a0  mov     rdi, rcx
0x1400214a3  mov     rax, r10
0x1400214a6  mov     ebp, r9d
0x1400214a9  sar     rax, 6
0x1400214ad  lea     rcx, qword_14003E600
0x1400214b4  and     r10d, 3Fh
0x1400214b8  add     rbp, r8
0x1400214bb  mov     rsi, r8
0x1400214be  mov     rax, [rcx+rax*8]
0x1400214c2  lea     rdx, [r10+r10*8]
0x1400214c6  mov     r14, [rax+rdx*8+28h]
0x1400214cb  xor     eax, eax
0x1400214cd  mov     [rdi], rax
0x1400214d0  mov     [rdi+8], eax
0x1400214d3  cmp     r8, rbp
0x1400214d6  jnb     loc_140021560
0x1400214dc  lea     rbx, [rsp+1468h+Buffer]
0x1400214e1  cmp     rsi, rbp
0x1400214e4  jnb     short loc_140021514
0x1400214e6  movzx   eax, word ptr [rsi]
0x1400214e9  add     rsi, 2
0x1400214ed  cmp     ax, 0Ah
0x1400214f1  jnz     short loc_140021500
0x1400214f3  add     dword ptr [rdi+8], 2
0x1400214f7  mov     word ptr [rbx], 0Dh
0x1400214fc  add     rbx, 2
0x140021500  mov     [rbx], ax
0x140021503  add     rbx, 2
0x140021507  lea     rax, [rsp+1468h+var_2A]
0x14002150f  cmp     rbx, rax
0x140021512  jb      short loc_1400214E1
0x140021514  and     [rsp+1468h+NumberOfBytesWritten], 0
0x140021519  lea     rax, [rsp+1468h+Buffer]
0x14002151e  and     [rsp+1468h+var_1448], 0
0x140021524  lea     r9, [rsp+1468h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140021529  sub     rbx, rax
0x14002152c  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x140021531  sar     rbx, 1
0x140021534  mov     rcx, r14; hFile
0x140021537  add     ebx, ebx
0x140021539  mov     r8d, ebx; nNumberOfBytesToWrite
0x14002153c  call    cs:WriteFile
0x140021542  test    eax, eax
0x140021544  jz      short loc_140021558
0x140021546  mov     eax, [rsp+1468h+NumberOfBytesWritten]
0x14002154a  add     [rdi+4], eax
0x14002154d  cmp     eax, ebx
0x14002154f  jb      short loc_140021560
0x140021551  cmp     rsi, rbp
0x140021554  jb      short loc_1400214DC
0x140021556  jmp     short loc_140021560
0x140021558  call    cs:GetLastError
0x14002155e  mov     [rdi], eax
0x140021560  mov     rax, rdi
0x140021563  mov     rcx, [rsp+1468h+var_28]
0x14002156b  xor     rcx, rsp; StackCookie
0x14002156e  call    __security_check_cookie
0x140021573  lea     r11, [rsp+1468h+var_18]
0x14002157b  mov     rbx, [r11+20h]
0x14002157f  mov     rbp, [r11+30h]
0x140021583  mov     rsp, r11
0x140021586  pop     r14
0x140021588  pop     rdi
0x140021589  pop     rsi
0x14002158a  retn
```

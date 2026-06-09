# HandleEndOfRead

- ea: `0x1800071c4`
- end: `0x18000730f`
- name: `HandleEndOfRead`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180006570`
- `0x18000d3e0`

## callees

- `0x1800071c4`
- `0x1800080dc`
- `0x1800096b8`
- `0x18000bce4`
- `0x18000dbb4`
- `0x18000e61c`

## import_xrefs

- `msvcrt!free` at `0x1800072f6`
- `msvcrt!free` at `0x1800072f6`
- `msvcrt!atoi` at `0x1800072d4`
- `msvcrt!atoi` at `0x1800072d4`

## pseudocode

```c
__int64 __fastcall HandleEndOfRead(_QWORD *a1, __int64 a2)
{
  unsigned int *v4; // r9
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  char *v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rax
  const char *v12; // rdx
  char *v13; // rcx
  char v14; // r8
  char *v15; // rax
  int v16; // eax
  unsigned int v17; // edi
  int v19; // [rsp+30h] [rbp+8h] BYREF
  char *v20; // [rsp+40h] [rbp+18h]

  v19 = 0;
  CPreAllocatedResizeBuffer<unsigned char>::append(a1[1284], &v19, 4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    v4 = (unsigned int *)a1[1284];
    if ( !*((_QWORD *)v4 + 6) )
      v4 += 2;
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids, *v4);
  }
  v5 = (_QWORD *)a1[1284];
  v6 = v5[6];
  v7 = v6;
  if ( !v6 )
  {
    v7 = v5[3];
    ++v5;
  }
  v8 = a1[6];
  if ( !v8 )
    v8 = a1[3];
  v9 = (char *)RPCToServer(a2, v8, *v5, v7);
  v20 = v9;
  if ( !v9 )
  {
    v10 = 26;
    v9 = (char *)MmAllocate(0x1Au);
    v11 = 2147483646;
    v12 = "500 Internal server error";
    v13 = v9;
    do
    {
      if ( !v11 )
        break;
      v14 = *v12;
      if ( !*v12 )
        break;
      ++v12;
      *v13++ = v14;
      --v11;
      --v10;
    }
    while ( v10 );
    v15 = v13 - 1;
    if ( v10 )
      v15 = v13;
    *v15 = 0;
    v20 = v9;
  }
  v16 = atoi(v9);
  v17 = SendResponse(a2, v9, v16 < 500);
  free(v9);
  return v17;
}

```

## disassembly

```asm
0x1800071c4  mov     rax, rsp
0x1800071c7  mov     [rax+10h], rbx
0x1800071cb  mov     [rax+20h], rsi
0x1800071cf  push    rdi
0x1800071d0  sub     rsp, 20h
0x1800071d4  mov     rsi, rdx
0x1800071d7  mov     rbx, rcx
0x1800071da  mov     dword ptr [rax+8], 0
0x1800071e1  mov     r8d, 4
0x1800071e7  lea     rdx, [rax+8]
0x1800071eb  mov     rcx, [rcx+2820h]
0x1800071f2  call    ?append@?$CPreAllocatedResizeBuffer@E@@QEAAXPEBE_K@Z; CPreAllocatedResizeBuffer<uchar>::append(uchar const *,unsigned __int64)
0x1800071f7  lea     rax, WPP_GLOBAL_Control
0x1800071fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180007205  cmp     rcx, rax
0x180007208  jz      short loc_18000723C
0x18000720a  test    byte ptr [rcx+6Ch], 4
0x18000720e  jz      short loc_18000723C
0x180007210  mov     r9, [rbx+2820h]
0x180007217  lea     rax, [r9+8]
0x18000721b  cmp     qword ptr [r9+30h], 0
0x180007220  cmovz   r9, rax
0x180007224  mov     edx, 10h
0x180007229  mov     r9d, [r9]
0x18000722c  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x180007233  mov     rcx, [rcx+60h]
0x180007237  call    WPP_SF_d
0x18000723c  mov     rcx, [rbx+2820h]
0x180007243  mov     rdx, [rcx+30h]
0x180007247  test    rdx, rdx
0x18000724a  mov     r9, rdx
0x18000724d  jnz     short loc_180007253
0x18000724f  mov     r9, [rcx+18h]
0x180007253  lea     rax, [rcx+8]
0x180007257  test    rdx, rdx
0x18000725a  cmovz   rcx, rax
0x18000725e  mov     rdx, [rbx+30h]
0x180007262  test    rdx, rdx
0x180007265  jnz     short loc_18000726B
0x180007267  mov     rdx, [rbx+18h]
0x18000726b  mov     r8, [rcx]
0x18000726e  mov     rcx, rsi
0x180007271  call    RPCToServer
0x180007276  mov     rbx, rax
0x180007279  mov     [rsp+28h+arg_10], rax
0x18000727e  test    rax, rax
0x180007281  jnz     short loc_1800072D1
0x180007283  lea     edi, [rax+1Ah]
0x180007286  mov     ecx, edi; unsigned __int64
0x180007288  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000728d  mov     rbx, rax
0x180007290  mov     eax, 7FFFFFFEh
0x180007295  lea     rdx, a500InternalSer; "500 Internal server error"
0x18000729c  mov     rcx, rbx
0x18000729f  test    rax, rax
0x1800072a2  jz      short loc_1800072BE
0x1800072a4  mov     r8b, [rdx]
0x1800072a7  test    r8b, r8b
0x1800072aa  jz      short loc_1800072BE
0x1800072ac  inc     rdx
0x1800072af  mov     [rcx], r8b
0x1800072b2  inc     rcx
0x1800072b5  dec     rax
0x1800072b8  sub     rdi, 1
0x1800072bc  jnz     short loc_18000729F
0x1800072be  lea     rax, [rcx-1]
0x1800072c2  test    rdi, rdi
0x1800072c5  cmovnz  rax, rcx
0x1800072c9  mov     byte ptr [rax], 0
0x1800072cc  mov     [rsp+28h+arg_10], rbx
0x1800072d1  mov     rcx, rbx; String
0x1800072d4  call    cs:__imp_atoi
0x1800072da  xor     r8d, r8d
0x1800072dd  cmp     eax, 1F4h
0x1800072e2  setl    r8b
0x1800072e6  mov     rdx, rbx
0x1800072e9  mov     rcx, rsi
0x1800072ec  call    SendResponse
0x1800072f1  mov     edi, eax
0x1800072f3  mov     rcx, rbx; Block
0x1800072f6  call    cs:__imp_free
0x1800072fc  nop
0x1800072fd  mov     eax, edi
0x1800072ff  mov     rbx, [rsp+28h+arg_8]
0x180007304  mov     rsi, [rsp+28h+arg_18]
0x180007309  add     rsp, 20h
0x18000730d  pop     rdi
0x18000730e  retn
```

# SerializeUpdateExParams

- ea: `0x180009e14`
- end: `0x180009f21`
- name: `SerializeUpdateExParams`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180009280`

## callees

- `0x1800096c0`
- `0x1800097c4`
- `0x180009cfc`
- `0x180009e14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009e70`

## pseudocode

```c
__int64 __fastcall SerializeUpdateExParams(__int128 *a1, _QWORD *a2, _DWORD *a3)
{
  int v4; // ecx
  int v7; // ecx
  int v8; // ecx
  unsigned int v9; // edi
  _OWORD *v10; // rax
  __int128 v11; // xmm0

  *a2 = 0;
  v4 = *((_DWORD *)a1 + 34);
  *a3 = 0;
  v7 = v4 - 2;
  if ( !v7 )
    return (unsigned int)SerializePerformanceParams(a1);
  v8 = v7 - 1;
  if ( !v8 )
    return (unsigned int)SerializeTlsParams(a1);
  if ( v8 == 2 )
    return (unsigned int)SerializeTlsSessionTicketKeys(a1);
  v9 = 8;
  v10 = HeapAlloc(NtCurrentPeb()->ProcessHeap, 8u, 0xA8u);
  if ( v10 )
  {
    v11 = *a1;
    v9 = 0;
    *a2 = v10;
    *a3 = 168;
    *v10 = v11;
    v10[1] = a1[1];
    v10[2] = a1[2];
    v10[3] = a1[3];
    v10[4] = a1[4];
    v10[5] = a1[5];
    v10[6] = a1[6];
    v10[7] = a1[7];
    v10[8] = a1[8];
    v10[9] = a1[9];
    *((_QWORD *)v10 + 20) = *((_QWORD *)a1 + 20);
  }
  return v9;
}

```

## disassembly

```asm
0x180009e14  push    rbx
0x180009e16  push    rsi
0x180009e17  push    rdi
0x180009e18  push    r14
0x180009e1a  sub     rsp, 28h
0x180009e1e  mov     rbx, rcx
0x180009e21  mov     qword ptr [rdx], 0
0x180009e28  mov     ecx, [rcx+88h]
0x180009e2e  mov     rsi, r8
0x180009e31  mov     dword ptr [r8], 0
0x180009e38  mov     r14, rdx
0x180009e3b  sub     ecx, 2
0x180009e3e  jz      loc_180009F0B
0x180009e44  sub     ecx, 1
0x180009e47  jz      loc_180009F01
0x180009e4d  cmp     ecx, 2
0x180009e50  jz      loc_180009EF7
0x180009e56  mov     rcx, gs:60h
0x180009e5f  mov     edi, 8
0x180009e64  mov     r8d, 0A8h; dwBytes
0x180009e6a  mov     edx, edi; dwFlags
0x180009e6c  mov     rcx, [rcx+30h]; hHeap
0x180009e70  call    cs:__imp_HeapAlloc
0x180009e76  mov     rcx, rax
0x180009e79  test    rax, rax
0x180009e7c  jz      loc_180009F15
0x180009e82  movups  xmm0, xmmword ptr [rbx]
0x180009e85  xor     edi, edi
0x180009e87  mov     [r14], rcx
0x180009e8a  mov     dword ptr [rsi], 0A8h
0x180009e90  movups  xmmword ptr [rax], xmm0
0x180009e93  movups  xmm1, xmmword ptr [rbx+10h]
0x180009e97  movups  xmmword ptr [rax+10h], xmm1
0x180009e9b  movups  xmm0, xmmword ptr [rbx+20h]
0x180009e9f  movups  xmmword ptr [rax+20h], xmm0
0x180009ea3  movups  xmm1, xmmword ptr [rbx+30h]
0x180009ea7  movups  xmmword ptr [rax+30h], xmm1
0x180009eab  movups  xmm0, xmmword ptr [rbx+40h]
0x180009eaf  movups  xmmword ptr [rax+40h], xmm0
0x180009eb3  movups  xmm1, xmmword ptr [rbx+50h]
0x180009eb7  movups  xmmword ptr [rax+50h], xmm1
0x180009ebb  movups  xmm0, xmmword ptr [rbx+60h]
0x180009ebf  movups  xmmword ptr [rax+60h], xmm0
0x180009ec3  movups  xmm1, xmmword ptr [rbx+70h]
0x180009ec7  movups  xmmword ptr [rax+70h], xmm1
0x180009ecb  movups  xmm0, xmmword ptr [rbx+80h]
0x180009ed2  movups  xmmword ptr [rax+80h], xmm0
0x180009ed9  movups  xmm1, xmmword ptr [rbx+90h]
0x180009ee0  movups  xmmword ptr [rax+90h], xmm1
0x180009ee7  mov     rax, [rbx+0A0h]
0x180009eee  mov     [rcx+0A0h], rax
0x180009ef5  jmp     short loc_180009F15
0x180009ef7  mov     rcx, rbx
0x180009efa  call    SerializeTlsSessionTicketKeys
0x180009eff  jmp     short loc_180009F13
0x180009f01  mov     rcx, rbx
0x180009f04  call    SerializeTlsParams
0x180009f09  jmp     short loc_180009F13
0x180009f0b  mov     rcx, rbx
0x180009f0e  call    SerializePerformanceParams
0x180009f13  mov     edi, eax
0x180009f15  mov     eax, edi
0x180009f17  add     rsp, 28h
0x180009f1b  pop     r14
0x180009f1d  pop     rdi
0x180009f1e  pop     rsi
0x180009f1f  pop     rbx
0x180009f20  retn
```

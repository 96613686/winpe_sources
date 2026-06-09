# transportDec_Open(TRANSPORT_TYPE,uint,uint)

- ea: `0x18000546c`
- end: `0x1800055e3`
- name: `?transportDec_Open@@YAPEAUTRANSPORTDEC@@W4TRANSPORT_TYPE@@II@Z`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005288`

## callees

- `0x18000546c`
- `0x1800408b0`
- `0x180040904`
- `0x18004b6d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005484`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800054be`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180005484`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800054be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005551`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005551`

## pseudocode

```c
char *__fastcall transportDec_Open(int a1, __int64 a2, unsigned int a3)
{
  char *v5; // rax
  char *v6; // rbx
  int v7; // edi
  void *v8; // rax
  unsigned int i; // r8d
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdx
  void **v14; // rbx
  int v15; // edi
  int v16; // edi
  int v17; // edi
  struct TRANSPORTDEC *v18; // [rsp+68h] [rbp+20h] BYREF

  v5 = (char *)calloc(1u, 0xF30u);
  v18 = (struct TRANSPORTDEC *)v5;
  v6 = v5;
  if ( v5 )
  {
    *(_DWORD *)v5 = a1;
    if ( a1 )
    {
      v7 = a1 - 1;
      if ( v7 )
      {
        v15 = v7 - 1;
        if ( v15 )
        {
          v16 = v15 - 4;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              if ( v17 != 3 )
              {
                FreeRam_TransportDecoder(&v18);
                return 0;
              }
            }
          }
          *((_WORD *)v5 + 115) = 256;
        }
        else
        {
          v5[210] = 1;
          CDKcrcInit((struct CDK_CRCINFO *)(v5 + 216), 0x8005u, 0xFFFFu, 0x10u);
          *(_WORD *)(v6 + 211) = 256;
          *((_DWORD *)v6 + 961) = 0;
        }
      }
    }
    v8 = calloc(0x8000u, 1u);
    *((_QWORD *)v6 + 23) = v8;
    if ( v8 )
    {
      if ( a3 <= 1 )
      {
        for ( i = 0; i < a3; *(_QWORD *)&v6[8 * v12 + 136] = 0 )
        {
          v10 = *((_QWORD *)v6 + 23);
          v11 = i++;
          v12 = 6 * v11;
          *(_QWORD *)&v6[8 * v12 + 144] = 0;
          *(_QWORD *)&v6[8 * v12 + 152] = 0;
          *(_QWORD *)&v6[8 * v12 + 160] = v10;
          *(_DWORD *)&v6[8 * v12 + 168] = 0x8000;
          *(_QWORD *)&v6[8 * v12 + 172] = 0x40000;
        }
        *((_DWORD *)v6 + 966) = 0;
        return v6;
      }
      transportDec_Close(&v18);
    }
    else
    {
      v14 = (void **)(v6 + 184);
      if ( v14 )
      {
        free(*v14);
        *v14 = 0;
      }
      FreeRam_TransportDecoder(&v18);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000546c  push    rbx
0x18000546e  push    rbp
0x18000546f  push    rsi
0x180005470  push    rdi
0x180005471  sub     rsp, 28h
0x180005475  mov     edi, ecx
0x180005477  mov     edx, 0F30h; Size
0x18000547c  mov     ecx, 1; Count
0x180005481  mov     esi, r8d
0x180005484  call    cs:__imp_calloc
0x18000548b  nop     dword ptr [rax+rax+00h]
0x180005490  xor     ebp, ebp
0x180005492  mov     [rsp+48h+arg_18], rax
0x180005497  mov     rbx, rax
0x18000549a  test    rax, rax
0x18000549d  jz      loc_18000556A
0x1800054a3  mov     [rax], edi
0x1800054a5  test    edi, edi
0x1800054a7  jz      short loc_1800054B2
0x1800054a9  sub     edi, 1
0x1800054ac  jnz     loc_18000556E
0x1800054b2  mov     edi, 8000h
0x1800054b7  mov     edx, 1; Size
0x1800054bc  mov     ecx, edi; Count
0x1800054be  call    cs:__imp_calloc
0x1800054c5  nop     dword ptr [rax+rax+00h]
0x1800054ca  mov     [rbx+0B8h], rax
0x1800054d1  test    rax, rax
0x1800054d4  jz      short loc_180005545
0x1800054d6  cmp     esi, 1
0x1800054d9  ja      loc_1800055D7
0x1800054df  mov     r8d, ebp
0x1800054e2  test    esi, esi
0x1800054e4  jz      short loc_180005532
0x1800054e6  mov     rcx, [rbx+0B8h]
0x1800054ed  mov     eax, r8d
0x1800054f0  inc     r8d
0x1800054f3  lea     rdx, [rax+rax*2]
0x1800054f7  add     rdx, rdx
0x1800054fa  mov     [rbx+rdx*8+90h], rbp
0x180005502  mov     [rbx+rdx*8+98h], rbp
0x18000550a  mov     [rbx+rdx*8+0A0h], rcx
0x180005512  mov     [rbx+rdx*8+0A8h], edi
0x180005519  mov     qword ptr [rbx+rdx*8+0ACh], 40000h
0x180005525  mov     [rbx+rdx*8+88h], rbp
0x18000552d  cmp     r8d, esi
0x180005530  jb      short loc_1800054E6
0x180005532  mov     [rbx+0F18h], ebp
0x180005538  mov     rax, rbx
0x18000553b  add     rsp, 28h
0x18000553f  pop     rdi
0x180005540  pop     rsi
0x180005541  pop     rbp
0x180005542  pop     rbx
0x180005543  retn
0x180005545  add     rbx, 0B8h
0x18000554c  jz      short loc_180005560
0x18000554e  mov     rcx, [rbx]; Block
0x180005551  call    cs:__imp_free
0x180005558  nop     dword ptr [rax+rax+00h]
0x18000555d  mov     [rbx], rbp
0x180005560  lea     rcx, [rsp+48h+arg_18]; struct TRANSPORTDEC **
0x180005565  call    ?FreeRam_TransportDecoder@@YAXPEAPEAUTRANSPORTDEC@@@Z; FreeRam_TransportDecoder(TRANSPORTDEC * *)
0x18000556a  xor     eax, eax
0x18000556c  jmp     short loc_18000553B
0x18000556e  sub     edi, 1
0x180005571  jz      short loc_18000559F
0x180005573  sub     edi, 4
0x180005576  jz      short loc_180005591
0x180005578  sub     edi, 1
0x18000557b  jz      short loc_180005591
0x18000557d  cmp     edi, 3
0x180005580  jz      short loc_180005591
0x180005582  lea     rcx, [rsp+48h+arg_18]; struct TRANSPORTDEC **
0x180005587  call    ?FreeRam_TransportDecoder@@YAXPEAPEAUTRANSPORTDEC@@@Z; FreeRam_TransportDecoder(TRANSPORTDEC * *)
0x18000558c  mov     rbx, rbp
0x18000558f  jmp     short loc_180005538
0x180005591  mov     word ptr [rax+0E6h], 100h
0x18000559a  jmp     loc_1800054B2
0x18000559f  lea     rcx, [rax+0D8h]; struct CDK_CRCINFO *
0x1800055a6  mov     byte ptr [rax+0D2h], 1
0x1800055ad  mov     edx, 8005h; unsigned int
0x1800055b2  mov     r9d, 10h; unsigned int
0x1800055b8  mov     r8d, 0FFFFh; unsigned int
0x1800055be  call    ?CDKcrcInit@@YAXPEAUCDK_CRCINFO@@III@Z; CDKcrcInit(CDK_CRCINFO *,uint,uint,uint)
0x1800055c3  mov     word ptr [rbx+0D3h], 100h
0x1800055cc  mov     [rbx+0F04h], ebp
0x1800055d2  jmp     loc_1800054B2
0x1800055d7  lea     rcx, [rsp+48h+arg_18]; struct TRANSPORTDEC **
0x1800055dc  call    ?transportDec_Close@@YAXPEAPEAUTRANSPORTDEC@@@Z; transportDec_Close(TRANSPORTDEC * *)
0x1800055e1  jmp     short loc_18000556A
```

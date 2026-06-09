# CSingleSideReducer::~CSingleSideReducer(void)

- ea: `0x100437180`
- end: `0x1004373c2`
- name: `??1CSingleSideReducer@@UEAA@XZ`
- size: `578`
- prototype: `void __fastcall(CSingleSideReducer *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x100403880`
- `0x1004162a0`
- `0x100437140`
- `0x10046ac6c`
- `0x1004729a4`
- `0x100472ca0`

## callees

- `0x100437180`
- `0x100439420`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437239`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043726f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004372ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004372f3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437335`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437374`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437239`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043726f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004372ac`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004372f3`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437335`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437374`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSingleSideReducer::~CSingleSideReducer(CSingleSideReducer *this)
{
  unsigned int v2; // ebp
  int v3; // eax
  unsigned int v4; // r8d
  int v5; // ecx
  __int64 v6; // rdx
  __int64 v7; // rdi
  __int64 v8; // rbx
  unsigned int v9; // esi
  __int64 v10; // rax
  void *v11; // rdx
  void *v12; // rdx

  *(_QWORD *)this = &CSingleSideReducer::`vftable';
  v2 = 0;
  while ( 1 )
  {
    v3 = *((_DWORD *)this + 33);
    v4 = *((_DWORD *)this + 37);
    v5 = v3 - 1;
    if ( !v3 )
      v5 = 0;
    if ( v2 >= *((_DWORD *)this + 36) + v4 * v5 )
      break;
    v6 = v2 % v4;
    v7 = 9 * v6;
    v8 = *(_QWORD *)(*((_QWORD *)this + 17) + 8LL * (v2 / v4));
    v9 = 0;
    if ( *(_DWORD *)(v8 + 72LL * (unsigned int)v6 + 20) )
    {
      do
      {
        v10 = *(_QWORD *)(v8 + 8 * v7 + 24);
        if ( g_SOSHost )
          (*(void (__fastcall **)(_QWORD, _QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj, *(_QWORD *)(v10 + 8LL * v9));
        else
          free(*(void **)(v10 + 8LL * v9));
        ++v9;
      }
      while ( v9 < *(_DWORD *)(v8 + 8 * v7 + 20) );
    }
    if ( g_SOSHost )
    {
      if ( *(_QWORD *)(v8 + 8 * v7 + 24) )
        (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
    }
    else
    {
      free(*(void **)(v8 + 8 * v7 + 24));
    }
    *(_QWORD *)(v8 + 8 * v7 + 24) = 0;
    *(_QWORD *)(v8 + 8 * v7 + 16) = 0;
    *(_DWORD *)(v8 + 8 * v7 + 32) = 0;
    if ( g_SOSHost )
    {
      if ( *(_QWORD *)(v8 + 8 * v7 + 48) )
        (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
    }
    else
    {
      free(*(void **)(v8 + 8 * v7 + 48));
    }
    *(_QWORD *)(v8 + 8 * v7 + 48) = 0;
    *(_QWORD *)(v8 + 8 * v7 + 40) = 0;
    if ( g_SOSHost )
    {
      if ( !*(_QWORD *)(v8 + 8 * v7 + 64) )
        goto LABEL_22;
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
      *(_QWORD *)(v8 + 8 * v7 + 64) = 0;
      *(_QWORD *)(v8 + 8 * v7 + 56) = 0;
      ++v2;
    }
    else
    {
      free(*(void **)(v8 + 8 * v7 + 64));
LABEL_22:
      *(_QWORD *)(v8 + 8 * v7 + 64) = 0;
      *(_QWORD *)(v8 + 8 * v7 + 56) = 0;
      ++v2;
    }
  }
  v11 = (void *)*((_QWORD *)this + 23);
  if ( g_SOSHost )
  {
    if ( v11 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v11);
  }
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 22) = 0;
  v12 = (void *)*((_QWORD *)this + 21);
  if ( g_SOSHost )
  {
    if ( v12 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v12);
  }
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 20) = 0;
  ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>((char *)this + 128);
  *((_QWORD *)this + 6) = &IMglGeometrySink::`vftable';
  *(_QWORD *)this = &IMglGeometrySink::`vftable';
}

```

## disassembly

```asm
0x100437180  mov     [rsp+arg_0], rcx
0x100437185  push    rsi
0x100437186  push    rdi
0x100437187  push    r12
0x100437189  push    r14
0x10043718b  push    r15
0x10043718d  sub     rsp, 30h
0x100437191  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x10043719a  mov     [rsp+58h+arg_8], rbx
0x10043719f  mov     [rsp+58h+arg_10], rbp
0x1004371a4  mov     r14, rcx
0x1004371a7  lea     rax, ??_7CSingleSideReducer@@6B@; const CSingleSideReducer::`vftable'
0x1004371ae  mov     [rcx], rax
0x1004371b1  xor     r12d, r12d
0x1004371b4  mov     ebp, r12d
0x1004371b7  nop     word ptr [rax+rax+00000000h]
0x1004371c0  mov     eax, [r14+84h]
0x1004371c7  mov     r8d, [r14+94h]
0x1004371ce  lea     ecx, [rax-1]
0x1004371d1  test    eax, eax
0x1004371d3  cmovz   ecx, r12d
0x1004371d7  imul    ecx, r8d
0x1004371db  add     ecx, [r14+90h]
0x1004371e2  cmp     ebp, ecx
0x1004371e4  jnb     loc_10043730A
0x1004371ea  xor     edx, edx
0x1004371ec  mov     eax, ebp
0x1004371ee  div     r8d
0x1004371f1  mov     rbx, [r14+88h]
0x1004371f8  lea     rdi, [rdx+rdx*8]
0x1004371fc  mov     rbx, [rbx+rax*8]
0x100437200  mov     esi, r12d
0x100437203  cmp     [rbx+rdi*8+14h], r12d
0x100437208  jbe     short loc_100437247
0x10043720a  nop     word ptr [rax+rax+00h]
0x100437210  mov     ecx, esi
0x100437212  mov     rax, [rbx+rdi*8+18h]
0x100437217  mov     rdx, [rax+rcx*8]
0x10043721b  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r12; SOS_AutoHost g_SOSHost
0x100437222  jz      short loc_100437236
0x100437224  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10043722b  mov     rax, [rcx]
0x10043722e  call    qword ptr [rax+80h]
0x100437234  jmp     short loc_10043723F
0x100437236  mov     rcx, rdx; Block
0x100437239  call    cs:__imp_free
0x10043723f  inc     esi
0x100437241  cmp     esi, [rbx+rdi*8+14h]
0x100437245  jb      short loc_100437210
0x100437247  mov     rdx, [rbx+rdi*8+18h]
0x10043724c  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r12; SOS_AutoHost g_SOSHost
0x100437253  jz      short loc_10043726C
0x100437255  test    rdx, rdx
0x100437258  jz      short loc_100437275
0x10043725a  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100437261  mov     rax, [rcx]
0x100437264  call    qword ptr [rax+80h]
0x10043726a  jmp     short loc_100437275
0x10043726c  mov     rcx, rdx; Block
0x10043726f  call    cs:__imp_free
0x100437275  mov     [rbx+rdi*8+18h], r12
0x10043727a  mov     [rbx+rdi*8+10h], r12
0x10043727f  mov     [rbx+rdi*8+20h], r12d
0x100437284  mov     rdx, [rbx+rdi*8+30h]
0x100437289  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r12; SOS_AutoHost g_SOSHost
0x100437290  jz      short loc_1004372A9
0x100437292  test    rdx, rdx
0x100437295  jz      short loc_1004372B2
0x100437297  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10043729e  mov     rax, [rcx]
0x1004372a1  call    qword ptr [rax+80h]
0x1004372a7  jmp     short loc_1004372B2
0x1004372a9  mov     rcx, rdx; Block
0x1004372ac  call    cs:__imp_free
0x1004372b2  mov     [rbx+rdi*8+30h], r12
0x1004372b7  mov     [rbx+rdi*8+28h], r12
0x1004372bc  mov     rdx, [rbx+rdi*8+40h]
0x1004372c1  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, r12; SOS_AutoHost g_SOSHost
0x1004372c8  jz      short loc_1004372F0
0x1004372ca  test    rdx, rdx
0x1004372cd  jz      short loc_1004372F9
0x1004372cf  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x1004372d6  mov     rax, [rcx]
0x1004372d9  call    qword ptr [rax+80h]
0x1004372df  mov     [rbx+rdi*8+40h], r12
0x1004372e4  mov     [rbx+rdi*8+38h], r12
0x1004372e9  inc     ebp
0x1004372eb  jmp     loc_1004371C0
0x1004372f0  mov     rcx, rdx; Block
0x1004372f3  call    cs:__imp_free
0x1004372f9  mov     [rbx+rdi*8+40h], r12
0x1004372fe  mov     [rbx+rdi*8+38h], r12
0x100437303  inc     ebp
0x100437305  jmp     loc_1004371C0
0x10043730a  mov     rdx, [r14+0B8h]
0x100437311  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100437319  jz      short loc_100437332
0x10043731b  test    rdx, rdx
0x10043731e  jz      short loc_10043733B
0x100437320  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100437327  mov     rax, [rcx]
0x10043732a  call    qword ptr [rax+80h]
0x100437330  jmp     short loc_10043733B
0x100437332  mov     rcx, rdx; Block
0x100437335  call    cs:__imp_free
0x10043733b  mov     [r14+0B8h], r12
0x100437342  mov     [r14+0B0h], r12
0x100437349  mov     rdx, [r14+0A8h]
0x100437350  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100437358  jz      short loc_100437371
0x10043735a  test    rdx, rdx
0x10043735d  jz      short loc_10043737A
0x10043735f  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100437366  mov     rax, [rcx]
0x100437369  call    qword ptr [rax+80h]
0x10043736f  jmp     short loc_10043737A
0x100437371  mov     rcx, rdx; Block
0x100437374  call    cs:__imp_free
0x10043737a  mov     [r14+0A8h], r12
0x100437381  mov     [r14+0A0h], r12
0x100437388  lea     rcx, [r14+80h]
0x10043738f  call    ??1?$ArrayOverPages@UShapeData@CSingleSideReducer@@V?$Default_Allocator@UShapeData@CSingleSideReducer@@@@@@QEAA@XZ; ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(void)
0x100437394  nop
0x100437395  lea     rax, [r14+30h]
0x100437399  mov     [rsp+58h+arg_0], rax
0x10043739e  lea     rcx, ??_7IMglGeometrySink@@6B@; const IMglGeometrySink::`vftable'
0x1004373a5  mov     [rax], rcx
0x1004373a8  mov     [r14], rcx
0x1004373ab  mov     rbx, [rsp+58h+arg_8]
0x1004373b0  mov     rbp, [rsp+58h+arg_10]
0x1004373b5  add     rsp, 30h
0x1004373b9  pop     r15
0x1004373bb  pop     r14
0x1004373bd  pop     r12
0x1004373bf  pop     rdi
0x1004373c0  pop     rsi
0x1004373c1  retn
```

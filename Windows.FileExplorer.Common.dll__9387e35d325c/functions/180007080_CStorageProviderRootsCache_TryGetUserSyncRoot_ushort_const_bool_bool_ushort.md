# CStorageProviderRootsCache::TryGetUserSyncRoot(ushort const *,bool,bool &,ushort * *)

- ea: `0x180007080`
- end: `0x18000733a`
- name: `?TryGetUserSyncRoot@CStorageProviderRootsCache@@QEAAJPEBG_NAEA_NPEAPEAG@Z`
- size: `698`
- prototype: `__int64 __fastcall(CStorageProviderRootsCache *__hidden this, const unsigned __int16 *, bool, bool *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008130`

## callees

- `0x180007080`
- `0x1800077c8`
- `0x180013ce0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007135`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071c8`

## string_xrefs

- `0x18000724e`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x1800072e5`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CStorageProviderRootsCache::TryGetUserSyncRoot(
        CStorageProviderRootsCache *this,
        const unsigned __int16 *a2,
        char a3,
        bool *a4,
        unsigned __int16 **a5)
{
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // rbx
  const WCHAR *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  const WCHAR *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int16 *v17; // rdi
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rsi
  unsigned __int16 *v20; // rax
  int v21; // r9d
  unsigned int v22; // ebp
  unsigned __int16 *v23; // rdx
  unsigned __int16 *v24; // rcx
  __int64 v26; // rcx
  _WORD *v27; // rax
  __int64 v28; // rcx
  int v29; // eax
  unsigned int v30; // ebx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *a4 = 0;
  v9 = 0;
  *a5 = 0;
  v10 = -1;
  while ( 1 )
  {
    if ( v9 >= *((_QWORD *)this + 71) )
      return 0;
    v11 = a2;
    v12 = *(_QWORD *)(8 * v9 + *((_QWORD *)this + 70));
    v13 = *(_QWORD *)(v12 + 8);
    if ( !a2 )
      v11 = &String1;
    if ( v13 != -1 )
    {
      v14 = *(const WCHAR **)v12;
      if ( v14 )
        goto LABEL_10;
      goto LABEL_50;
    }
    if ( !*(_QWORD *)v12 )
    {
      LODWORD(v13) = 0;
LABEL_50:
      v14 = &String1;
      goto LABEL_10;
    }
    v13 = -1;
    do
      ++v13;
    while ( *(_WORD *)(*(_QWORD *)v12 + 2 * v13) );
    v14 = *(const WCHAR **)v12;
LABEL_10:
    if ( CompareStringOrdinal(v14, v13, v11, -(a2 != 0), 1) == 2 )
      break;
    ++v9;
  }
  _mm_lfence();
  v15 = *((_QWORD *)this + 70);
  if ( !a3 )
  {
    v16 = *(_QWORD *)(v15 + 8 * v9);
    *a5 = 0;
    v17 = *(unsigned __int16 **)(v16 + 24);
    if ( !v17 )
    {
      v22 = -2147023728;
      goto LABEL_34;
    }
    v18 = *(_QWORD *)(v16 + 32);
    if ( v18 == -1 )
    {
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
    }
    do
      ++v10;
    while ( v17[v10] );
    if ( v18 == -1 )
    {
      v18 = v10;
    }
    else if ( v18 < v10 )
    {
      v10 = v18;
    }
    v19 = v18 + 1;
    if ( v18 + 1 < v18 || !is_mul_ok(v19, 2u) )
    {
      v22 = -2147024362;
      v21 = -2147024362;
      goto LABEL_33;
    }
    v20 = (unsigned __int16 *)CoTaskMemAlloc(2 * v19);
    if ( !v20 )
    {
      v22 = -2147024882;
      v21 = -2147024882;
      goto LABEL_33;
    }
    *v20 = 0;
    if ( v19 )
    {
      if ( v19 <= 0x7FFFFFFF )
      {
        v21 = 0;
        v22 = 0;
        if ( v10 > 0x7FFFFFFE )
        {
          *v20 = 0;
        }
        else
        {
          v23 = v20;
          do
          {
            if ( !v10 )
              break;
            if ( !*v17 )
              break;
            *v23++ = *v17++;
            --v10;
            --v19;
          }
          while ( v19 );
          v24 = v23 - 1;
          if ( v19 )
            v24 = v23;
          *v24 = 0;
        }
LABEL_32:
        *a5 = v20;
LABEL_33:
        if ( v21 < 0 )
        {
LABEL_34:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCFA,
            (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
            (const char *)v22,
            bIgnoreCase);
          return v22;
        }
LABEL_36:
        *a4 = 1;
        return 0;
      }
      *v20 = 0;
    }
    v21 = 0;
    v22 = 0;
    goto LABEL_32;
  }
  v26 = *(_QWORD *)(v15 + 8 * v9);
  v27 = *(_WORD **)(v26 + 48);
  v28 = v26 + 48;
  if ( !v27 || !*v27 )
    return 2147943568LL;
  v29 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CopyTo(v28, a5);
  v30 = v29;
  if ( v29 >= 0 )
    goto LABEL_36;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCF6,
    (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
    (const char *)(unsigned int)v29,
    bIgnoreCase);
  return v30;
}

```

## disassembly

```asm
0x180007080  mov     [rsp+arg_8], rbx
0x180007085  mov     [rsp+arg_10], rbp
0x18000708a  push    rsi
0x18000708b  push    rdi
0x18000708c  push    r12
0x18000708e  push    r13
0x180007090  push    r15
0x180007092  sub     rsp, 30h
0x180007096  mov     r12, [rsp+58h+arg_20]
0x18000709e  mov     r13, r9
0x1800070a1  movzx   r15d, r8b
0x1800070a5  mov     byte ptr [r9], 0
0x1800070a9  mov     rbp, rdx
0x1800070ac  mov     [rsp+58h+arg_0], r14
0x1800070b1  mov     rdi, rcx
0x1800070b4  xor     esi, esi
0x1800070b6  mov     qword ptr [r12], 0
0x1800070be  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800070c5  lea     r10, String1
0x1800070cc  cmp     rsi, [rdi+238h]
0x1800070d3  jnb     loc_18000728F
0x1800070d9  mov     rax, [rdi+230h]
0x1800070e0  lea     r14, ds:0[rsi*8]
0x1800070e8  mov     r8, rbp
0x1800070eb  mov     rcx, [r14+rax]
0x1800070ef  mov     rax, rbp
0x1800070f2  neg     rax
0x1800070f5  sbb     r9d, r9d; cchCount2
0x1800070f8  mov     rdx, [rcx+8]
0x1800070fc  test    rbp, rbp
0x1800070ff  cmovz   r8, r10; lpString2
0x180007103  cmp     rdx, rbx
0x180007106  jnz     loc_18000730A
0x18000710c  mov     rax, [rcx]
0x18000710f  test    rax, rax
0x180007112  jz      loc_18000731E
0x180007118  mov     rdx, rbx
0x18000711b  nop     dword ptr [rax+rax+00h]
0x180007120  inc     rdx; cchCount1
0x180007123  cmp     word ptr [rax+rdx*2], 0
0x180007128  jnz     short loc_180007120
0x18000712a  mov     rcx, rax; lpString1
0x18000712d  mov     [rsp+58h+bIgnoreCase], 1; int
0x180007135  call    cs:__imp_CompareStringOrdinal
0x18000713b  cmp     eax, 2
0x18000713e  jnz     loc_1800072B7
0x180007144  lfence
0x180007147  mov     rax, [rdi+230h]
0x18000714e  test    r15b, r15b
0x180007151  jnz     loc_180007293
0x180007157  mov     rax, [rax+r14]
0x18000715b  xor     r14d, r14d
0x18000715e  mov     [r12], r14
0x180007162  mov     rdi, [rax+18h]
0x180007166  test    rdi, rdi
0x180007169  jz      loc_180007300
0x18000716f  mov     rax, [rax+20h]
0x180007173  cmp     rax, rbx
0x180007176  jnz     short loc_180007190
0x180007178  mov     rax, rbx
0x18000717b  nop     dword ptr [rax+rax+00h]
0x180007180  inc     rax
0x180007183  cmp     [rdi+rax*2], r14w
0x180007188  jnz     short loc_180007180
0x18000718a  nop     word ptr [rax+rax+00h]
0x180007190  inc     rbx
0x180007193  cmp     [rdi+rbx*2], r14w
0x180007198  jnz     short loc_180007190
0x18000719a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000719e  jnz     loc_1800072AB
0x1800071a4  mov     rax, rbx
0x1800071a7  lea     rsi, [rax+1]
0x1800071ab  cmp     rsi, rax
0x1800071ae  jb      loc_180007280
0x1800071b4  mov     eax, 2
0x1800071b9  mul     rsi
0x1800071bc  test    rdx, rdx
0x1800071bf  jnz     loc_180007280
0x1800071c5  mov     rcx, rax; cb
0x1800071c8  call    cs:__imp_CoTaskMemAlloc
0x1800071ce  mov     r8, rax
0x1800071d1  test    rax, rax
0x1800071d4  jz      loc_1800072BF
0x1800071da  mov     [rax], r14w
0x1800071de  test    rsi, rsi
0x1800071e1  jz      loc_180007326
0x1800071e7  cmp     rsi, 7FFFFFFFh
0x1800071ee  ja      loc_180007322
0x1800071f4  mov     r9d, r14d
0x1800071f7  mov     ebp, r14d
0x1800071fa  cmp     rbx, 7FFFFFFEh
0x180007201  ja      loc_180007331
0x180007207  mov     rdx, rax
0x18000720a  nop     word ptr [rax+rax+00h]
0x180007210  test    rbx, rbx
0x180007213  jz      short loc_180007231
0x180007215  movzx   eax, word ptr [rdi]
0x180007218  test    ax, ax
0x18000721b  jz      short loc_180007231
0x18000721d  mov     [rdx], ax
0x180007220  add     rdi, 2
0x180007224  add     rdx, 2
0x180007228  dec     rbx
0x18000722b  sub     rsi, 1
0x18000722f  jnz     short loc_180007210
0x180007231  test    rsi, rsi
0x180007234  lea     rcx, [rdx-2]
0x180007238  cmovnz  rcx, rdx
0x18000723c  mov     [rcx], r14w
0x180007240  mov     [r12], r8
0x180007244  test    r9d, r9d
0x180007247  jns     short loc_18000728A
0x180007249  mov     rcx, [rsp+58h]; this
0x18000724e  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180007255  mov     r9d, ebp; char *
0x180007258  mov     edx, 0CFAh; void *
0x18000725d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007262  mov     eax, ebp
0x180007264  mov     r14, [rsp+58h+arg_0]
0x180007269  mov     rbx, [rsp+58h+arg_8]
0x18000726e  mov     rbp, [rsp+58h+arg_10]
0x180007273  add     rsp, 30h
0x180007277  pop     r15
0x180007279  pop     r13
0x18000727b  pop     r12
0x18000727d  pop     rdi
0x18000727e  pop     rsi
0x18000727f  retn
0x180007280  mov     ebp, 80070216h
0x180007285  mov     r9d, ebp
0x180007288  jmp     short loc_180007244
0x18000728a  mov     byte ptr [r13+0], 1
0x18000728f  xor     eax, eax
0x180007291  jmp     short loc_180007264
0x180007293  mov     rcx, [rax+r14]
0x180007297  mov     rax, [rcx+30h]
0x18000729b  add     rcx, 30h ; '0'
0x18000729f  test    rax, rax
0x1800072a2  jnz     short loc_1800072CC
0x1800072a4  mov     eax, 80070490h
0x1800072a9  jmp     short loc_180007264
0x1800072ab  cmp     rax, rbx
0x1800072ae  cmovb   rbx, rax
0x1800072b2  jmp     loc_1800071A7
0x1800072b7  inc     rsi
0x1800072ba  jmp     loc_1800070C5
0x1800072bf  mov     ebp, 8007000Eh
0x1800072c4  mov     r9d, ebp
0x1800072c7  jmp     loc_180007244
0x1800072cc  cmp     word ptr [rax], 0
0x1800072d0  jz      short loc_1800072A4
0x1800072d2  mov     rdx, r12
0x1800072d5  call    ?CopyTo@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CopyTo(ushort * *)
0x1800072da  mov     ebx, eax
0x1800072dc  test    eax, eax
0x1800072de  jns     short loc_18000728A
0x1800072e0  mov     rcx, [rsp+58h]; this
0x1800072e5  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x1800072ec  mov     r9d, eax; char *
0x1800072ef  mov     edx, 0CF6h; void *
0x1800072f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072f9  mov     eax, ebx
0x1800072fb  jmp     loc_180007264
0x180007300  mov     ebp, 80070490h
0x180007305  jmp     loc_180007249
0x18000730a  mov     rcx, [rcx]
0x18000730d  test    rcx, rcx
0x180007310  jnz     loc_18000712D
0x180007316  mov     rcx, r10
0x180007319  jmp     loc_18000712D
0x18000731e  xor     edx, edx
0x180007320  jmp     short loc_180007316
0x180007322  mov     [rax], r14w
0x180007326  mov     r9d, r14d
0x180007329  mov     ebp, r14d
0x18000732c  jmp     loc_180007240
0x180007331  mov     [rax], r14w
0x180007335  jmp     loc_180007240
```

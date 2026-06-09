# WimRemoveOverlay

- ea: `0x14002b7cc`
- end: `0x14002ba08`
- name: `WimRemoveOverlay`
- size: `572`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140026440`
- `0x140027410`

## callees

- `0x14000fce4`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002b454`
- `0x14002b7cc`
- `0x14002be3c`
- `0x14003c5c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9c0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b871`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b871`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b9d4`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b9d4`
- `FLTMGR!FltClose` at `0x14002b9e8`
- `FLTMGR!FltClose` at `0x14002b9e8`

## pseudocode

```c
__int64 __fastcall WimRemoveOverlay(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  __int64 result; // rax
  _DWORD *v5; // r15
  char *v6; // r14
  unsigned int v7; // ebx
  HANDLE v8; // rdi
  PVOID v9; // rsi
  size_t v10; // rdi
  char *PoolWithTag; // rax
  unsigned int v12; // esi
  unsigned int v13; // r13d
  char *v15; // r9
  unsigned int v16; // eax
  size_t v17; // rcx
  unsigned int *v18; // r12
  _DWORD *v19; // rdi
  unsigned int v20; // esi
  _DWORD *v21; // rax
  int v22; // eax
  HANDLE FileHandle; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+38h] [rbp-20h] BYREF
  size_t v25; // [rsp+40h] [rbp-18h]
  __int64 v27; // [rsp+A8h] [rbp+50h] BYREF
  SIZE_T NumberOfBytes; // [rsp+B0h] [rbp+58h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+60h] BYREF

  v27 = a2;
  LODWORD(NumberOfBytes) = 0;
  P = 0;
  FileHandle = 0;
  Object = 0;
  v3 = a1;
  result = WimReadOverlayConfig(a1, 0, &FileHandle, (PFILE_OBJECT *)&Object, &P, (ULONG *)&NumberOfBytes);
  if ( (int)result < 0 )
    return result;
  v5 = P;
  if ( WimFindOverlayInfo(P, &v27) )
  {
    v10 = (unsigned int)NumberOfBytes;
    PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x66637077u);
    v6 = PoolWithTag;
    if ( PoolWithTag )
    {
      v12 = v5[2];
      memset(PoolWithTag, 0, v10);
      v13 = 24;
      *(_OWORD *)v6 = *(_OWORD *)v5;
      *((_QWORD *)v6 + 2) = *((_QWORD *)v5 + 2);
      if ( (*((_DWORD *)v6 + 3))-- != 1 )
      {
        v13 = v12 * *((_DWORD *)v6 + 3) + 24;
        if ( v5[3] )
        {
          v15 = v6 + 24;
          v16 = 0;
          v17 = v12;
          P = v6 + 24;
          LODWORD(NumberOfBytes) = 0;
          v18 = v5 + 6;
          v25 = v12;
          do
          {
            if ( *(_QWORD *)v18 != a2 )
            {
              v19 = (_DWORD *)((char *)v5 + v18[2]);
              v20 = v19[2];
              memmove(v15, v18, v17);
              v21 = P;
              *((_DWORD *)P + 2) = v13;
              v21[3] = v20;
              memmove(&v6[v13], v19, v20);
              v13 += v20;
              v17 = v25;
              v16 = NumberOfBytes;
              v15 = (char *)P + v25;
              P = (char *)P + v25;
            }
            ++v16;
            v18 = (unsigned int *)((char *)v18 + v17);
            LODWORD(NumberOfBytes) = v16;
          }
          while ( v16 < v5[3] );
          v3 = a1;
        }
      }
      v22 = WimWriteOverlayConfig(v3, FileHandle, Object, v6, v13);
      v9 = 0;
      v8 = 0;
      v7 = v22;
      if ( v22 < 0 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Zd(
          WPP_GLOBAL_Control->AttachedDevice,
          49,
          (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
          v3 + 64,
          v22);
      goto LABEL_18;
    }
    v7 = -1073741670;
  }
  else
  {
    v6 = 0;
    v7 = -1073741275;
  }
  v8 = FileHandle;
  v9 = Object;
LABEL_18:
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  if ( v9 )
    ObfDereferenceObject(v9);
  if ( v8 )
    FltClose(v8);
  return v7;
}

```

## disassembly

```asm
0x14002b7cc  mov     [rsp-40h+arg_8], rdx
0x14002b7d1  mov     [rsp-40h+arg_0], rcx
0x14002b7d6  push    rbp
0x14002b7d7  push    rbx
0x14002b7d8  push    rsi
0x14002b7d9  push    rdi
0x14002b7da  push    r12
0x14002b7dc  push    r13
0x14002b7de  push    r14
0x14002b7e0  push    r15
0x14002b7e2  mov     rbp, rsp
0x14002b7e5  sub     rsp, 58h
0x14002b7e9  lea     rax, [rbp+NumberOfBytes]
0x14002b7ed  mov     dword ptr [rbp+NumberOfBytes], 0
0x14002b7f4  mov     [rsp+58h+var_30], rax
0x14002b7f9  lea     r9, [rbp+Object]
0x14002b7fd  lea     rax, [rbp+P]
0x14002b801  mov     [rbp+P], 0
0x14002b809  mov     rbx, rdx
0x14002b80c  mov     [rsp+58h+var_38], rax
0x14002b811  lea     r8, [rbp+FileHandle]
0x14002b815  mov     [rbp+FileHandle], 0
0x14002b81d  xor     edx, edx
0x14002b81f  mov     [rbp+Object], 0
0x14002b827  mov     r12, rcx
0x14002b82a  call    WimReadOverlayConfig
0x14002b82f  test    eax, eax
0x14002b831  js      loc_14002B9F6
0x14002b837  mov     r15, [rbp+P]
0x14002b83b  lea     rdx, [rbp+arg_8]
0x14002b83f  mov     rcx, r15
0x14002b842  call    WimFindOverlayInfo
0x14002b847  test    rax, rax
0x14002b84a  jnz     short loc_14002B861
0x14002b84c  xor     r14d, r14d
0x14002b84f  mov     ebx, 0C0000225h
0x14002b854  mov     rdi, [rbp+FileHandle]
0x14002b858  mov     rsi, [rbp+Object]
0x14002b85c  jmp     loc_14002B9A0
0x14002b861  mov     edi, dword ptr [rbp+NumberOfBytes]
0x14002b864  mov     r8d, 66637077h; Tag
0x14002b86a  mov     edx, edi; NumberOfBytes
0x14002b86c  mov     ecx, 1; PoolType
0x14002b871  call    cs:__imp_ExAllocatePoolWithTag
0x14002b878  nop     dword ptr [rax+rax+00h]
0x14002b87d  mov     r14, rax
0x14002b880  test    rax, rax
0x14002b883  jnz     short loc_14002B88C
0x14002b885  mov     ebx, 0C000009Ah
0x14002b88a  jmp     short loc_14002B854
0x14002b88c  mov     esi, [r15+8]
0x14002b890  mov     r8, rdi; Size
0x14002b893  xor     edx, edx; Val
0x14002b895  mov     rcx, r14; void *
0x14002b898  call    memset
0x14002b89d  movups  xmm0, xmmword ptr [r15]
0x14002b8a1  mov     r13d, 18h
0x14002b8a7  movups  xmmword ptr [r14], xmm0
0x14002b8ab  movsd   xmm1, qword ptr [r15+10h]
0x14002b8b1  movsd   qword ptr [r14+10h], xmm1
0x14002b8b7  add     dword ptr [r14+0Ch], 0FFFFFFFFh
0x14002b8bc  mov     eax, [r14+0Ch]
0x14002b8c0  jz      loc_14002B94C
0x14002b8c6  imul    eax, esi
0x14002b8c9  add     r13d, eax
0x14002b8cc  cmp     dword ptr [r15+0Ch], 0
0x14002b8d1  jbe     short loc_14002B94C
0x14002b8d3  lea     r9, [r14+18h]
0x14002b8d7  xor     eax, eax
0x14002b8d9  mov     ecx, esi
0x14002b8db  mov     [rbp+P], r9
0x14002b8df  mov     dword ptr [rbp+NumberOfBytes], eax
0x14002b8e2  lea     r12, [r15+18h]
0x14002b8e6  mov     [rbp+var_18], rcx
0x14002b8ea  cmp     [r12], rbx
0x14002b8ee  jz      short loc_14002B93A
0x14002b8f0  mov     edi, [r12+8]
0x14002b8f5  mov     r8, rcx; Size
0x14002b8f8  add     rdi, r15
0x14002b8fb  mov     rdx, r12; Src
0x14002b8fe  mov     rcx, r9; void *
0x14002b901  mov     esi, [rdi+8]
0x14002b904  call    memmove
0x14002b909  mov     rax, [rbp+P]
0x14002b90d  mov     r8d, esi; Size
0x14002b910  mov     ecx, r13d
0x14002b913  mov     rdx, rdi; Src
0x14002b916  add     rcx, r14; void *
0x14002b919  mov     [rax+8], r13d
0x14002b91d  mov     [rax+0Ch], esi
0x14002b920  call    memmove
0x14002b925  mov     r9, [rbp+P]
0x14002b929  add     r13d, esi
0x14002b92c  mov     rcx, [rbp+var_18]
0x14002b930  mov     eax, dword ptr [rbp+NumberOfBytes]
0x14002b933  add     r9, rcx
0x14002b936  mov     [rbp+P], r9
0x14002b93a  inc     eax
0x14002b93c  add     r12, rcx
0x14002b93f  mov     dword ptr [rbp+NumberOfBytes], eax
0x14002b942  cmp     eax, [r15+0Ch]
0x14002b946  jb      short loc_14002B8EA
0x14002b948  mov     r12, [rbp+arg_0]
0x14002b94c  mov     r8, [rbp+Object]
0x14002b950  mov     r9, r14
0x14002b953  mov     rdx, [rbp+FileHandle]
0x14002b957  mov     rcx, r12
0x14002b95a  mov     dword ptr [rsp+58h+var_38], r13d
0x14002b95f  call    WimWriteOverlayConfig
0x14002b964  xor     esi, esi
0x14002b966  xor     edi, edi
0x14002b968  mov     ebx, eax
0x14002b96a  test    eax, eax
0x14002b96c  jns     short loc_14002B9A0
0x14002b96e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b975  test    dword ptr [rcx+2Ch], 400h
0x14002b97c  jz      short loc_14002B9A0
0x14002b97e  cmp     byte ptr [rcx+29h], 2
0x14002b982  jb      short loc_14002B9A0
0x14002b984  mov     rcx, [rcx+18h]
0x14002b988  lea     r9, [r12+40h]
0x14002b98d  lea     edx, [rsi+31h]
0x14002b990  mov     dword ptr [rsp+58h+var_38], eax
0x14002b994  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b99b  call    WPP_SF_Zd
0x14002b9a0  test    r15, r15
0x14002b9a3  jz      short loc_14002B9B6
0x14002b9a5  xor     edx, edx; Tag
0x14002b9a7  mov     rcx, r15; P
0x14002b9aa  call    cs:__imp_ExFreePoolWithTag
0x14002b9b1  nop     dword ptr [rax+rax+00h]
0x14002b9b6  test    r14, r14
0x14002b9b9  jz      short loc_14002B9CC
0x14002b9bb  xor     edx, edx; Tag
0x14002b9bd  mov     rcx, r14; P
0x14002b9c0  call    cs:__imp_ExFreePoolWithTag
0x14002b9c7  nop     dword ptr [rax+rax+00h]
0x14002b9cc  test    rsi, rsi
0x14002b9cf  jz      short loc_14002B9E0
0x14002b9d1  mov     rcx, rsi; Object
0x14002b9d4  call    cs:__imp_ObfDereferenceObject
0x14002b9db  nop     dword ptr [rax+rax+00h]
0x14002b9e0  test    rdi, rdi
0x14002b9e3  jz      short loc_14002B9F4
0x14002b9e5  mov     rcx, rdi; FileHandle
0x14002b9e8  call    cs:__imp_FltClose
0x14002b9ef  nop     dword ptr [rax+rax+00h]
0x14002b9f4  mov     eax, ebx
0x14002b9f6  add     rsp, 58h
0x14002b9fa  pop     r15
0x14002b9fc  pop     r14
0x14002b9fe  pop     r13
0x14002ba00  pop     r12
0x14002ba02  pop     rdi
0x14002ba03  pop     rsi
0x14002ba04  pop     rbx
0x14002ba05  pop     rbp
0x14002ba06  retn
```

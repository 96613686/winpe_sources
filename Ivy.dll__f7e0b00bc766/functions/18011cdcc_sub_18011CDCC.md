# sub_18011CDCC

- ea: `0x18011cdcc`
- end: `0x18011cf7d`
- name: `sub_18011CDCC`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18011cf80`

## callees

- `0x180011ac4`
- `0x180011ae8`
- `0x180107898`
- `0x18011cdcc`
- `0x18011d7f4`
- `0x18016d174`
- `0x18016eaf0`

## import_xrefs

- `MSVCP140!_Mtx_unlock` at `0x18011ce40`
- `MSVCP140!_Mtx_unlock` at `0x18011ceee`
- `MSVCP140!_Mtx_unlock` at `0x18011ce40`
- `MSVCP140!_Mtx_unlock` at `0x18011ceee`

## string_xrefs

- `0x18011cf4c`: `Can't get value from enumerator outside data enumerate mode.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall sub_18011CDCC(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdi
  _QWORD *v5; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rbx
  void **v10; // [rsp+30h] [rbp-38h] BYREF
  _Mtx_t v11; // [rsp+38h] [rbp-30h]
  _DWORD *v12; // [rsp+40h] [rbp-28h]
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  sub_180107898(&v10, *(_QWORD *)(a1 + 16));
  v4 = *(_QWORD *)(a1 + 16);
  if ( !*(_DWORD *)(v4 + 104) )
  {
    sub_180011AE8(508642445, &qword_1801AB2B8);
    sub_180011AC4(508642445, "a lock is required in this context");
  }
  if ( *(_BYTE *)(a1 + 28) )
    v5 = 0;
  else
    v5 = *(_QWORD **)(v4 + 96);
  if ( v5 )
  {
    sub_18016D174(*v5, 20056, 0);
    if ( !*(_DWORD *)(a1 + 24) )
    {
      sub_180011AE8(508649494, &qword_1801AB2B8);
      sub_180011AC4(508649494, "Can't get value from enumerator outside data enumerate mode.");
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 32) + 24LL))(*(_QWORD *)(a1 + 32));
    (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(*(_QWORD *)v7 + 56LL))(v7, a2, &v13, 1);
    v8 = *(_QWORD *)(a1 + 16);
    if ( !*(_DWORD *)(v8 + 104) )
    {
      sub_180011AE8(508642445, &qword_1801AB2B8);
      sub_180011AC4(508642445, "a lock is required in this context");
    }
    if ( *(_BYTE *)(a1 + 28) )
      v9 = 0;
    else
      v9 = *(_QWORD **)(v8 + 96);
    if ( v9 )
      sub_18016D174(*v9, 20056, 0);
    sub_18011D7F4(v9 + 31, v13);
    v10 = &Ivy::Extras::ChartDataTransform::LockGuard::`vftable';
    --*v12;
    return Mtx_unlock(v11);
  }
  else
  {
    v10 = &Ivy::Extras::ChartDataTransform::LockGuard::`vftable';
    --*v12;
    return Mtx_unlock(v11);
  }
}

```

## disassembly

```asm
0x18011cdcc  mov     rax, rsp
0x18011cdcf  mov     [rax+10h], rbx
0x18011cdd3  mov     [rax+18h], rsi
0x18011cdd7  push    rdi
0x18011cdd8  sub     rsp, 60h
0x18011cddc  movaps  xmmword ptr [rax-18h], xmm6
0x18011cde0  mov     esi, edx
0x18011cde2  mov     rbx, rcx
0x18011cde5  mov     rdx, [rcx+10h]
0x18011cde9  lea     rcx, [rax-38h]
0x18011cded  call    sub_180107898
0x18011cdf2  mov     rdi, [rbx+10h]
0x18011cdf6  cmp     dword ptr [rdi+68h], 0
0x18011cdfa  jz      loc_18011CF18
0x18011ce00  cmp     byte ptr [rbx+1Ch], 0
0x18011ce04  jnz     short loc_18011CE0C
0x18011ce06  mov     rdi, [rdi+60h]
0x18011ce0a  jmp     short loc_18011CE0E
0x18011ce0c  xor     edi, edi
0x18011ce0e  test    rdi, rdi
0x18011ce11  jz      short loc_18011CE23
0x18011ce13  xor     r8d, r8d
0x18011ce16  mov     edx, 4E58h
0x18011ce1b  mov     rcx, [rdi]
0x18011ce1e  call    sub_18016D174
0x18011ce23  test    rdi, rdi
0x18011ce26  jnz     short loc_18011CE53
0x18011ce28  lea     rax, ??_7LockGuard@ChartDataTransform@Extras@Ivy@@6B@; const Ivy::Extras::ChartDataTransform::LockGuard::`vftable'
0x18011ce2f  mov     [rsp+68h+var_38], rax
0x18011ce34  mov     rax, [rsp+68h+var_28]
0x18011ce39  dec     dword ptr [rax]
0x18011ce3b  mov     rcx, [rsp+68h+var_30]; _Mtx_t
0x18011ce40  call    cs:_Mtx_unlock
0x18011ce46  movsd   xmm0, cs:X
0x18011ce4e  jmp     loc_18011CF01
0x18011ce53  mov     eax, [rbx+18h]
0x18011ce56  test    eax, eax
0x18011ce58  jz      loc_18011CF39
0x18011ce5e  xchg    ax, ax
0x18011ce60  mov     rcx, [rbx+20h]
0x18011ce64  mov     rax, [rcx]
0x18011ce67  mov     rax, [rax+18h]
0x18011ce6b  call    cs:__guard_dispatch_icall_fptr
0x18011ce71  mov     r10, rax
0x18011ce74  mov     rcx, [rax]
0x18011ce77  mov     rax, [rcx+38h]
0x18011ce7b  mov     r9d, 1
0x18011ce81  lea     r8, [rsp+68h+arg_0]
0x18011ce86  mov     edx, esi
0x18011ce88  mov     rcx, r10
0x18011ce8b  call    cs:__guard_dispatch_icall_fptr
0x18011ce91  mov     rax, [rbx+10h]
0x18011ce95  cmp     dword ptr [rax+68h], 0
0x18011ce99  jz      loc_18011CF5A
0x18011ce9f  cmp     byte ptr [rbx+1Ch], 0
0x18011cea3  jnz     short loc_18011CEAB
0x18011cea5  mov     rbx, [rax+60h]
0x18011cea9  jmp     short loc_18011CEAD
0x18011ceab  xor     ebx, ebx
0x18011cead  test    rbx, rbx
0x18011ceb0  jz      short loc_18011CEC2
0x18011ceb2  xor     r8d, r8d
0x18011ceb5  mov     edx, 4E58h
0x18011ceba  mov     rcx, [rbx]
0x18011cebd  call    sub_18016D174
0x18011cec2  lea     rcx, [rbx+0F8h]
0x18011cec9  mov     rdx, [rsp+68h+arg_0]
0x18011cece  call    sub_18011D7F4
0x18011ced3  movaps  xmm6, xmm0
0x18011ced6  lea     rax, ??_7LockGuard@ChartDataTransform@Extras@Ivy@@6B@; const Ivy::Extras::ChartDataTransform::LockGuard::`vftable'
0x18011cedd  mov     [rsp+68h+var_38], rax
0x18011cee2  mov     rax, [rsp+68h+var_28]
0x18011cee7  dec     dword ptr [rax]
0x18011cee9  mov     rcx, [rsp+68h+var_30]; _Mtx_t
0x18011ceee  call    cs:_Mtx_unlock
0x18011cef4  movaps  xmm0, xmm6
0x18011cef7  jmp     short loc_18011CF01
0x18011cef9  movsd   xmm0, cs:X
0x18011cf01  lea     r11, [rsp+68h+var_8]
0x18011cf06  mov     rbx, [r11+18h]
0x18011cf0a  mov     rsi, [r11+20h]
0x18011cf0e  movaps  xmm6, [rsp+68h+var_18]
0x18011cf13  mov     rsp, r11
0x18011cf16  pop     rdi
0x18011cf17  retn
0x18011cf18  lea     rdx, qword_1801AB2B8
0x18011cf1f  mov     ebx, 1E51448Dh
0x18011cf24  mov     ecx, ebx
0x18011cf26  call    sub_180011AE8
0x18011cf2b  lea     rdx, aALockIsRequire; "a lock is required in this context"
0x18011cf32  mov     ecx, ebx
0x18011cf34  call    sub_180011AC4
0x18011cf39  lea     rdx, qword_1801AB2B8
0x18011cf40  mov     ebx, 1E516016h
0x18011cf45  mov     ecx, ebx
0x18011cf47  call    sub_180011AE8
0x18011cf4c  lea     rdx, aCanTGetValueFr; "Can't get value from enumerator outside"...
0x18011cf53  mov     ecx, ebx
0x18011cf55  call    sub_180011AC4
0x18011cf5a  lea     rdx, qword_1801AB2B8
0x18011cf61  mov     ebx, 1E51448Dh
0x18011cf66  mov     ecx, ebx
0x18011cf68  call    sub_180011AE8
0x18011cf6d  lea     rdx, aALockIsRequire; "a lock is required in this context"
0x18011cf74  mov     ecx, ebx
0x18011cf76  call    sub_180011AC4
```

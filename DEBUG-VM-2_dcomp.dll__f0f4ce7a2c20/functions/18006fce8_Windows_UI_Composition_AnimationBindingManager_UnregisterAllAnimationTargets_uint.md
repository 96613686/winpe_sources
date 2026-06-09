# Windows::UI::Composition::AnimationBindingManager::UnregisterAllAnimationTargets(uint)

- ea: `0x18006fce8`
- end: `0x18006fe94`
- name: `?UnregisterAllAnimationTargets@AnimationBindingManager@Composition@UI@Windows@@QEAAXI@Z`
- size: `428`
- prototype: `void __fastcall(PRTL_GENERIC_TABLE Table, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18006fc44`

## callees

- `0x18000bc00`
- `0x18000bf80`
- `0x18000c01c`
- `0x18006fce8`
- `0x1800e77ac`
- `0x1800f6f34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18006fe5b`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18006fe89`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18006fe5b`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18006fe89`
- `ntdll!RtlDeleteElementGenericTable` at `0x18006fdfc`
- `ntdll!RtlDeleteElementGenericTable` at `0x18006fe45`
- `ntdll!RtlDeleteElementGenericTable` at `0x18006fdfc`
- `ntdll!RtlDeleteElementGenericTable` at `0x18006fe45`
- `ntdll!RtlLookupElementGenericTable` at `0x18006fd23`
- `ntdll!RtlLookupElementGenericTable` at `0x18006fd7b`
- `ntdll!RtlLookupElementGenericTable` at `0x18006fd23`
- `ntdll!RtlLookupElementGenericTable` at `0x18006fd7b`

## pseudocode

```c
void __fastcall Windows::UI::Composition::AnimationBindingManager::UnregisterAllAnimationTargets(
        PRTL_GENERIC_TABLE Table,
        int a2)
{
  int v2; // r14d
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  int *v6; // rsi
  int v7; // eax
  _QWORD *v8; // r12
  __int64 *v9; // r15
  __int64 v10; // r14
  unsigned int v11; // edx
  _QWORD *v12; // rcx
  int Buffer; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h]
  _DWORD v15[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v16; // [rsp+38h] [rbp-28h]
  _DWORD v17[2]; // [rsp+48h] [rbp-18h] BYREF
  __int128 v18; // [rsp+50h] [rbp-10h]
  struct _RTL_GENERIC_TABLE *Tablea; // [rsp+A0h] [rbp+40h]

  Buffer = a2;
  v2 = a2;
  v14 = 0;
  Tablea = Table + 1;
  v4 = RtlLookupElementGenericTable(Table + 1, &Buffer);
  v5 = v4;
  if ( v4 )
  {
    v6 = (int *)v4[1];
    if ( !v6 )
LABEL_4:
      Microsoft::WRL2::FailFast::Unexpected(0);
LABEL_5:
    if ( v6 )
    {
      v7 = *v6;
      v15[0] = v2;
      v15[1] = v7;
      v16 = 0;
      v8 = RtlLookupElementGenericTable(Table, v15);
      v9 = v8 + 2;
      if ( !v8[1] && !*v9 )
        goto LABEL_4;
      while ( 1 )
      {
        v10 = v8[1];
        if ( v10 )
        {
          v8[1] = *(_QWORD *)(v10 + 24);
        }
        else
        {
          v10 = *v9;
          if ( !*v9 )
          {
            v17[0] = *(_DWORD *)v8;
            v17[1] = *((_DWORD *)v8 + 1);
            v18 = 0;
            if ( !RtlDeleteElementGenericTable(Table, v17) )
              RaiseFailFastException(0, 0, 1u);
            v6 = (int *)*((_QWORD *)v6 + 1);
            v2 = a2;
            goto LABEL_5;
          }
          *v9 = *(_QWORD *)(v10 + 24);
        }
        Windows::UI::Composition::CompositionPropertyAnimator::RemoveTarget(*(Windows::UI::Composition::CompositionPropertyAnimator **)(v10 + 8));
        *(_QWORD *)(*(_QWORD *)(v10 + 8) + 176LL) = 0;
        Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock((void *)(v10 + 8));
        Windows::UI::Composition::ExpressionListEntry::`scalar deleting destructor'(
          (Windows::UI::Composition::ExpressionListEntry *)v10,
          v11);
      }
    }
    while ( 1 )
    {
      v12 = (_QWORD *)v5[1];
      if ( !v12 )
        break;
      v5[1] = v12[1];
      operator delete(v12, 0x10u);
    }
    v15[0] = *(_DWORD *)v5;
    *(_QWORD *)&v16 = 0;
    if ( !RtlDeleteElementGenericTable(Tablea, v15) )
      RaiseFailFastException(0, 0, 1u);
  }
}

```

## disassembly

```asm
0x18006fce8  mov     [rsp-38h+arg_10], rbx
0x18006fced  mov     [rsp-38h+arg_8], edx
0x18006fcf1  push    rbp
0x18006fcf2  push    rsi
0x18006fcf3  push    rdi
0x18006fcf4  push    r12
0x18006fcf6  push    r13
0x18006fcf8  push    r14
0x18006fcfa  push    r15
0x18006fcfc  mov     rbp, rsp
0x18006fcff  sub     rsp, 60h
0x18006fd03  lea     rbx, [rcx+48h]
0x18006fd07  mov     [rbp+Buffer], edx
0x18006fd0a  mov     r14d, edx
0x18006fd0d  mov     [rbp+var_38], 0
0x18006fd15  mov     r13, rcx
0x18006fd18  mov     [rbp+Table], rbx
0x18006fd1c  mov     rcx, rbx; Table
0x18006fd1f  lea     rdx, [rbp+Buffer]; Buffer
0x18006fd23  call    cs:__imp_RtlLookupElementGenericTable
0x18006fd29  mov     rdi, rax
0x18006fd2c  test    rax, rax
0x18006fd2f  jnz     short loc_18006FD49
0x18006fd31  mov     rbx, [rsp+60h+arg_10]
0x18006fd39  add     rsp, 60h
0x18006fd3d  pop     r15
0x18006fd3f  pop     r14
0x18006fd41  pop     r13
0x18006fd43  pop     r12
0x18006fd45  pop     rdi
0x18006fd46  pop     rsi
0x18006fd47  pop     rbp
0x18006fd48  retn
0x18006fd49  mov     rsi, [rax+8]
0x18006fd4d  test    rsi, rsi
0x18006fd50  jnz     short loc_18006FD5A
0x18006fd52  xor     ecx, ecx; char *
0x18006fd54  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
0x18006fd5a  test    rsi, rsi
0x18006fd5d  jz      loc_18006FE13
0x18006fd63  mov     eax, [rsi]
0x18006fd65  lea     rdx, [rbp+var_30]; Buffer
0x18006fd69  xorps   xmm0, xmm0
0x18006fd6c  mov     [rbp+var_30], r14d
0x18006fd70  mov     rcx, r13; Table
0x18006fd73  mov     [rbp+var_2C], eax
0x18006fd76  movdqu  [rbp+var_28], xmm0
0x18006fd7b  call    cs:__imp_RtlLookupElementGenericTable
0x18006fd81  mov     r12, rax
0x18006fd84  cmp     qword ptr [rax+8], 0
0x18006fd89  lea     r15, [rax+10h]
0x18006fd8d  jz      loc_18006FE72
0x18006fd93  mov     r14, [r12+8]
0x18006fd98  test    r14, r14
0x18006fd9b  jz      short loc_18006FDD2
0x18006fd9d  mov     rax, [r14+18h]
0x18006fda1  mov     [r12+8], rax
0x18006fda6  lea     rbx, [r14+8]
0x18006fdaa  mov     rcx, [rbx]; this
0x18006fdad  call    ?RemoveTarget@CompositionPropertyAnimator@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositionPropertyAnimator::RemoveTarget(void)
0x18006fdb2  mov     rax, [rbx]
0x18006fdb5  mov     rcx, rbx; void *
0x18006fdb8  mov     qword ptr [rax+0B0h], 0
0x18006fdc3  call    ?InternalUnlock@?$RefPtr@VCompositionPropertyAnimator@Composition@UI@Windows@@@WRL2@Microsoft@@IEAAXXZ; Microsoft::WRL2::RefPtr<Windows::UI::Composition::CompositionPropertyAnimator>::InternalUnlock(void)
0x18006fdc8  mov     rcx, r14; this
0x18006fdcb  call    ??_GExpressionListEntry@Composition@UI@Windows@@QEAAPEAXI@Z; Windows::UI::Composition::ExpressionListEntry::`scalar deleting destructor'(uint)
0x18006fdd0  jmp     short loc_18006FD93
0x18006fdd2  mov     r14, [r15]
0x18006fdd5  test    r14, r14
0x18006fdd8  jnz     loc_18006FE66
0x18006fdde  mov     eax, [r12]
0x18006fde2  lea     rdx, [rbp+var_18]; Buffer
0x18006fde6  mov     [rbp+var_18], eax
0x18006fde9  xorps   xmm0, xmm0
0x18006fdec  mov     eax, [r12+4]
0x18006fdf1  mov     rcx, r13; Table
0x18006fdf4  mov     [rbp+var_14], eax
0x18006fdf7  movdqu  [rbp+var_10], xmm0
0x18006fdfc  call    cs:__imp_RtlDeleteElementGenericTable
0x18006fe02  test    al, al
0x18006fe04  jz      short loc_18006FE81
0x18006fe06  mov     rsi, [rsi+8]
0x18006fe0a  mov     r14d, [rbp+arg_8]
0x18006fe0e  jmp     loc_18006FD5A
0x18006fe13  mov     rcx, [rdi+8]; void *
0x18006fe17  test    rcx, rcx
0x18006fe1a  jz      short loc_18006FE30
0x18006fe1c  mov     rax, [rcx+8]
0x18006fe20  mov     edx, 10h; unsigned __int64
0x18006fe25  mov     [rdi+8], rax
0x18006fe29  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006fe2e  jmp     short loc_18006FE13
0x18006fe30  mov     eax, [rdi]
0x18006fe32  lea     rdx, [rbp+var_30]; Buffer
0x18006fe36  mov     rcx, [rbp+Table]; Table
0x18006fe3a  mov     [rbp+var_30], eax
0x18006fe3d  mov     qword ptr [rbp+var_28], 0
0x18006fe45  call    cs:__imp_RtlDeleteElementGenericTable
0x18006fe4b  test    al, al
0x18006fe4d  jnz     loc_18006FD31
0x18006fe53  xor     edx, edx; pContextRecord
0x18006fe55  xor     ecx, ecx; pExceptionRecord
0x18006fe57  lea     r8d, [rdx+1]; dwFlags
0x18006fe5b  call    cs:__imp_RaiseFailFastException
0x18006fe61  jmp     loc_18006FD31
0x18006fe66  mov     rax, [r14+18h]
0x18006fe6a  mov     [r15], rax
0x18006fe6d  jmp     loc_18006FDA6
0x18006fe72  cmp     qword ptr [r15], 0
0x18006fe76  jz      loc_18006FD52
0x18006fe7c  jmp     loc_18006FD93
0x18006fe81  xor     edx, edx; pContextRecord
0x18006fe83  xor     ecx, ecx; pExceptionRecord
0x18006fe85  lea     r8d, [rdx+1]; dwFlags
0x18006fe89  call    cs:__imp_RaiseFailFastException
0x18006fe8f  jmp     loc_18006FE06
```

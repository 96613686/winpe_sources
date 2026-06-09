# SupportedFileTypes::ClassifyFile(ushort const *)

- ea: `0x180022924`
- end: `0x180022adf`
- name: `?ClassifyFile@SupportedFileTypes@@AEBAKPEBG@Z`
- size: `443`
- prototype: `unsigned int(SupportedFileTypes *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f1c0`
- `0x1800286a4`
- `0x1800723fc`

## callees

- `0x180022924`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180022a2b`
- `KERNEL32!CompareStringW` at `0x180022a2b`
- `KERNEL32!CompareStringOrdinal` at `0x180022969`
- `KERNEL32!CompareStringOrdinal` at `0x1800229c0`
- `KERNEL32!CompareStringOrdinal` at `0x180022969`
- `KERNEL32!CompareStringOrdinal` at `0x1800229c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800229f3`
- `KERNEL32!LeaveCriticalSection` at `0x180022ac6`
- `KERNEL32!LeaveCriticalSection` at `0x1800229f3`
- `KERNEL32!LeaveCriticalSection` at `0x180022ac6`
- `KERNEL32!EnterCriticalSection` at `0x180022987`
- `KERNEL32!EnterCriticalSection` at `0x180022a49`
- `KERNEL32!EnterCriticalSection` at `0x180022987`
- `KERNEL32!EnterCriticalSection` at `0x180022a49`
- `SHLWAPI!PathFindExtensionW` at `0x180022946`
- `SHLWAPI!PathFindExtensionW` at `0x180022946`

## pseudocode

```c
__int64 __fastcall SupportedFileTypes::ClassifyFile(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  const WCHAR *ExtensionW; // rsi
  HANDLE *p_OwningThread; // rbp
  __int64 SpinCount; // rdi
  char v8; // r12
  unsigned __int64 i; // r14
  __int64 v10; // rdi
  int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  char *v15; // rdx
  char *v16; // r8

  v2 = 0;
  if ( a2 )
  {
    ExtensionW = PathFindExtensionW(a2);
    if ( CompareStringOrdinal(ExtensionW, -1, L".jpg", -1, 1) == 2 )
      return 1;
    p_OwningThread = &this->OwningThread;
    EnterCriticalSection(this + 53);
    SpinCount = this[52].SpinCount;
    v8 = 0;
    for ( i = 0; i < 4; ++i )
    {
      if ( CompareStringOrdinal(ExtensionW, -1, (LPCWCH)p_OwningThread + 262 * SpinCount, -1, 1) == 2 )
      {
        v2 = *((_DWORD *)p_OwningThread + 131 * SpinCount + 130);
        v8 = 1;
        break;
      }
      if ( SpinCount )
        --SpinCount;
      else
        SpinCount = 3;
    }
    LeaveCriticalSection(this + 53);
    if ( !v8 )
    {
      v10 = *(_QWORD *)&this->LockCount;
      v2 = 0;
      while ( v10 )
      {
        v11 = CompareStringW(0x400u, 1u, *(PCNZWCH *)v10, -1, ExtensionW, -1);
        if ( v11 != 1 )
        {
          if ( v11 == 2 )
            v2 = *(_DWORD *)(v10 + 8);
          break;
        }
        v10 = *(_QWORD *)(v10 + 16);
      }
      EnterCriticalSection(this + 53);
      v12 = 2147483646;
      v13 = 260;
      v14 = (this[52].SpinCount + 1) & -(__int64)(this[52].SpinCount < 3);
      this[52].SpinCount = v14;
      v15 = (char *)p_OwningThread + 524 * v14;
      do
      {
        if ( !v12 )
          break;
        if ( !*ExtensionW )
          break;
        *(_WORD *)v15 = *ExtensionW++;
        v15 += 2;
        --v12;
        --v13;
      }
      while ( v13 );
      v16 = v15 - 2;
      if ( v13 )
        v16 = v15;
      *(_WORD *)v16 = 0;
      *((_DWORD *)p_OwningThread + 131 * this[52].SpinCount + 130) = v2;
      LeaveCriticalSection(this + 53);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180022924  push    rbx
0x180022926  push    rbp
0x180022927  push    rsi
0x180022928  push    rdi
0x180022929  push    r12
0x18002292b  push    r13
0x18002292d  push    r14
0x18002292f  push    r15
0x180022931  sub     rsp, 38h
0x180022935  xor     ebx, ebx
0x180022937  mov     r15, rcx
0x18002293a  test    rdx, rdx
0x18002293d  jz      loc_180022ACC
0x180022943  mov     rcx, rdx; pszPath
0x180022946  call    cs:__imp_PathFindExtensionW
0x18002294c  lea     r8, pszExt; ".jpg"
0x180022953  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18002295b  mov     rsi, rax
0x18002295e  or      eax, 0FFFFFFFFh
0x180022961  mov     r9d, eax; cchCount2
0x180022964  mov     edx, eax; cchCount1
0x180022966  mov     rcx, rsi; lpString1
0x180022969  call    cs:__imp_CompareStringOrdinal
0x18002296f  cmp     eax, 2
0x180022972  jnz     short loc_18002297C
0x180022974  lea     eax, [rbx+1]
0x180022977  jmp     loc_180022ACE
0x18002297c  lea     rbp, [r15+10h]
0x180022980  lea     rcx, [rbp+838h]; lpCriticalSection
0x180022987  call    cs:__imp_EnterCriticalSection
0x18002298d  mov     rdi, [rbp+830h]
0x180022994  xor     r12b, r12b
0x180022997  xor     r14d, r14d
0x18002299a  cmp     r14, 4
0x18002299e  jnb     short loc_1800229E9
0x1800229a0  or      eax, 0FFFFFFFFh
0x1800229a3  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800229ab  imul    r13, rdi, 20Ch
0x1800229b2  mov     r9d, eax; cchCount2
0x1800229b5  mov     edx, eax; cchCount1
0x1800229b7  add     r13, rbp
0x1800229ba  mov     rcx, rsi; lpString1
0x1800229bd  mov     r8, r13; lpString2
0x1800229c0  call    cs:__imp_CompareStringOrdinal
0x1800229c6  cmp     eax, 2
0x1800229c9  jz      short loc_1800229DF
0x1800229cb  test    rdi, rdi
0x1800229ce  jnz     short loc_1800229D7
0x1800229d0  mov     edi, 3
0x1800229d5  jmp     short loc_1800229DA
0x1800229d7  dec     rdi
0x1800229da  inc     r14
0x1800229dd  jmp     short loc_18002299A
0x1800229df  mov     ebx, [r13+208h]
0x1800229e6  mov     r12b, 1
0x1800229e9  lea     r13, [rbp+838h]
0x1800229f0  mov     rcx, r13; lpCriticalSection
0x1800229f3  call    cs:__imp_LeaveCriticalSection
0x1800229f9  xor     r14d, r14d
0x1800229fc  test    r12b, r12b
0x1800229ff  jnz     loc_180022ACC
0x180022a05  mov     rdi, [r15+8]
0x180022a09  mov     ebx, r14d
0x180022a0c  test    rdi, rdi
0x180022a0f  jz      short loc_180022A46
0x180022a11  mov     r8, [rdi]; lpString1
0x180022a14  or      eax, 0FFFFFFFFh
0x180022a17  mov     [rsp+78h+cchCount2], eax; cchCount2
0x180022a1b  mov     r9d, eax; cchCount1
0x180022a1e  mov     ecx, 400h; Locale
0x180022a23  mov     qword ptr [rsp+78h+bIgnoreCase], rsi; lpString2
0x180022a28  lea     edx, [rax+2]; dwCmpFlags
0x180022a2b  call    cs:__imp_CompareStringW
0x180022a31  mov     ecx, eax
0x180022a33  sub     ecx, 1
0x180022a36  jnz     short loc_180022A3E
0x180022a38  mov     rdi, [rdi+10h]
0x180022a3c  jmp     short loc_180022A0C
0x180022a3e  cmp     ecx, 1
0x180022a41  jnz     short loc_180022A46
0x180022a43  mov     ebx, [rdi+8]
0x180022a46  mov     rcx, r13; lpCriticalSection
0x180022a49  call    cs:__imp_EnterCriticalSection
0x180022a4f  mov     rax, [rbp+830h]
0x180022a56  mov     r8d, 7FFFFFFEh
0x180022a5c  cmp     rax, 3
0x180022a60  mov     r9d, 104h
0x180022a66  lea     rcx, [rax+1]
0x180022a6a  sbb     rax, rax
0x180022a6d  and     rax, rcx
0x180022a70  imul    rdx, rax, 20Ch
0x180022a77  mov     [rbp+830h], rax
0x180022a7e  add     rdx, rbp
0x180022a81  test    r8, r8
0x180022a84  jz      short loc_180022AA2
0x180022a86  movzx   eax, word ptr [rsi]
0x180022a89  test    ax, ax
0x180022a8c  jz      short loc_180022AA2
0x180022a8e  mov     [rdx], ax
0x180022a91  add     rsi, 2
0x180022a95  add     rdx, 2
0x180022a99  dec     r8
0x180022a9c  sub     r9, 1
0x180022aa0  jnz     short loc_180022A81
0x180022aa2  lea     r8, [rdx-2]
0x180022aa6  test    r9, r9
0x180022aa9  mov     rcx, r13; lpCriticalSection
0x180022aac  cmovnz  r8, rdx
0x180022ab0  mov     [r8], r14w
0x180022ab4  imul    rdx, [rbp+830h], 20Ch
0x180022abf  mov     [rdx+rbp+208h], ebx
0x180022ac6  call    cs:__imp_LeaveCriticalSection
0x180022acc  mov     eax, ebx
0x180022ace  add     rsp, 38h
0x180022ad2  pop     r15
0x180022ad4  pop     r14
0x180022ad6  pop     r13
0x180022ad8  pop     r12
0x180022ada  pop     rdi
0x180022adb  pop     rsi
0x180022adc  pop     rbp
0x180022add  pop     rbx
0x180022ade  retn
```

# wil::details_abi::SemaphoreValue::CreateFromValueInternal(wchar_t const *,bool,unsigned __int64)

- ea: `0x180071ea0`
- end: `0x1800721a3`
- name: `?CreateFromValueInternal@SemaphoreValue@details_abi@wil@@AEAAJPEB_W_N_K@Z`
- size: `771`
- prototype: `__int64 __fastcall(wil::details_abi::SemaphoreValue *__hidden this, const wchar_t *, bool, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180073c10`

## callees

- `0x18000d4b0`
- `0x1800442c0`
- `0x180070c00`
- `0x1800719d0`
- `0x180071ea0`
- `0x1801f7110`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007205b`
- `KERNEL32!GetLastError` at `0x18007213d`
- `KERNEL32!GetLastError` at `0x18007205b`
- `KERNEL32!GetLastError` at `0x18007213d`
- `KERNEL32!CreateSemaphoreExW` at `0x180072004`
- `KERNEL32!CreateSemaphoreExW` at `0x180072101`
- `KERNEL32!CreateSemaphoreExW` at `0x180072004`
- `KERNEL32!CreateSemaphoreExW` at `0x180072101`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::CreateFromValueInternal(
        wil::details_abi::SemaphoreValue *this,
        const wchar_t *a2,
        char a3,
        unsigned __int64 a4)
{
  WCHAR *v8; // rcx
  __int64 v9; // rdx
  signed __int64 v10; // r10
  WCHAR v11; // ax
  WCHAR *v12; // rax
  __int64 v13; // rcx
  WCHAR *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rax
  char *v20; // r9
  WCHAR v21; // r8
  WCHAR *v22; // rax
  unsigned __int64 v23; // rbp
  LONG v24; // r11d
  LONG v25; // r14d
  LONG v26; // r8d
  wil::details *v27; // rcx
  HANDLE Semaphore; // rsi
  int LastErrorFailHr; // eax
  unsigned int v30; // esi
  __int64 v32; // rcx
  WCHAR *v33; // rax
  __int64 v34; // rax
  WCHAR *v35; // rcx
  __int64 v36; // rbx
  char *v37; // rdx
  WCHAR v38; // ax
  WCHAR *v39; // rax
  wil::details *v40; // rcx
  HANDLE v41; // rbx
  int v42; // eax
  unsigned int v43; // ebx
  DWORD dwFlags; // [rsp+20h] [rbp-268h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-268h]
  WCHAR Name[264]; // [rsp+30h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( a3 )
  {
    if ( (a4 & 0xC000000000000000uLL) == 0 )
      goto LABEL_3;
LABEL_49:
    wil::details::in1diag3::_FailFastImmediate_Unexpected(this);
  }
  if ( (a4 & 0xFFFFFFFF80000000uLL) != 0 )
    goto LABEL_49;
LABEL_3:
  v8 = Name;
  v9 = 260;
  v10 = (char *)a2 - (char *)Name;
  do
  {
    if ( v9 == -2147483386 )
      break;
    v11 = *(WCHAR *)((char *)v8 + v10);
    if ( !v11 )
      break;
    *v8++ = v11;
    --v9;
  }
  while ( v9 );
  v12 = v8 - 1;
  if ( v9 )
    v12 = v8;
  v13 = 260;
  *v12 = 0;
  v14 = Name;
  do
  {
    if ( !*v14 )
      break;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = 2147483646;
  v16 = 260 - v13;
  if ( v13 )
  {
    v17 = &Name[v16];
    v18 = 260 - v16;
    if ( v16 != 260 )
    {
      v19 = 2147483646;
      v20 = (char *)((char *)L"_p0" - (char *)v17);
      do
      {
        if ( !v19 )
          break;
        v21 = *(WCHAR *)((char *)v17 + (_QWORD)v20);
        if ( !v21 )
          break;
        *v17 = v21;
        --v19;
        ++v17;
        --v18;
      }
      while ( v18 );
    }
    v22 = v17 - 1;
    if ( v18 )
      v22 = v17;
    *v22 = 0;
  }
  v23 = a4 >> 31;
  v24 = a4 & 0x7FFFFFFF;
  v25 = 1;
  v26 = 1;
  if ( v24 )
    v26 = v24;
  Semaphore = CreateSemaphoreExW(0, v24, v26, Name, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      this,
      Semaphore);
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v27);
    v30 = LastErrorFailHr;
    if ( LastErrorFailHr < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"wil",
        (const char *)(unsigned int)LastErrorFailHr,
        dwFlags);
      return v30;
    }
  }
  if ( a3 )
  {
    v32 = 260;
    v33 = Name;
    do
    {
      if ( !*v33 )
        break;
      ++v33;
      --v32;
    }
    while ( v32 );
    v34 = 260 - v32;
    if ( v32 )
    {
      v35 = &Name[v34];
      v36 = 260 - v34;
      if ( 260 != v34 )
      {
        v37 = (char *)((char *)L"h" - (char *)v35);
        do
        {
          if ( !v15 )
            break;
          v38 = *(WCHAR *)((char *)v35 + (_QWORD)v37);
          if ( !v38 )
            break;
          *v35 = v38;
          --v15;
          ++v35;
          --v36;
        }
        while ( v36 );
      }
      v39 = v35 - 1;
      if ( v36 )
        v39 = v35;
      *v39 = 0;
    }
    if ( (_DWORD)v23 )
      v25 = v23;
    v41 = CreateSemaphoreExW(0, v23, v25, Name, 0, 0x1F0003u);
    if ( v41 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        (char *)this + 8,
        v41);
    }
    else
    {
      v42 = wil::details::GetLastErrorFailHr(v40);
      v43 = v42;
      if ( v42 < 0 )
      {
        _mm_lfence();
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8D,
          (unsigned int)"wil",
          (const char *)(unsigned int)v42,
          dwFlagsa);
        return v43;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180071ea0  push    r13
0x180071ea2  push    r15
0x180071ea4  sub     rsp, 278h
0x180071eab  mov     rax, cs:__security_cookie
0x180071eb2  xor     rax, rsp
0x180071eb5  mov     [rsp+288h+var_48], rax
0x180071ebd  mov     r11, r9
0x180071ec0  movzx   r15d, r8b
0x180071ec4  mov     r10, rdx
0x180071ec7  mov     r13, rcx
0x180071eca  test    r8b, r8b
0x180071ecd  jnz     loc_180072043
0x180071ed3  test    r9, 0FFFFFFFF80000000h
0x180071eda  jnz     loc_18007219D
0x180071ee0  mov     [rsp+288h+arg_8], rbx
0x180071ee8  lea     rax, [rsp+288h+Name]
0x180071eed  mov     [rsp+288h+var_18], rbp
0x180071ef5  lea     rcx, [rsp+288h+Name]
0x180071efa  mov     [rsp+288h+var_20], rsi
0x180071f02  mov     ebx, 104h
0x180071f07  mov     [rsp+288h+var_28], rdi
0x180071f0f  mov     edx, ebx
0x180071f11  mov     [rsp+288h+var_30], r12
0x180071f19  sub     r10, rax
0x180071f1c  mov     [rsp+288h+var_38], r14
0x180071f24  lea     rax, [rdx+7FFFFEFAh]
0x180071f2b  test    rax, rax
0x180071f2e  jz      short loc_180071F47
0x180071f30  movzx   eax, word ptr [r10+rcx]
0x180071f35  test    ax, ax
0x180071f38  jz      short loc_180071F47
0x180071f3a  mov     [rcx], ax
0x180071f3d  add     rcx, 2
0x180071f41  sub     rdx, 1
0x180071f45  jnz     short loc_180071F24
0x180071f47  test    rdx, rdx
0x180071f4a  lea     rax, [rcx-2]
0x180071f4e  cmovnz  rax, rcx
0x180071f52  xor     r12d, r12d
0x180071f55  mov     rcx, rbx
0x180071f58  mov     [rax], r12w
0x180071f5c  lea     rax, [rsp+288h+Name]
0x180071f61  cmp     [rax], r12w
0x180071f65  jz      short loc_180071F71
0x180071f67  add     rax, 2
0x180071f6b  sub     rcx, 1
0x180071f6f  jnz     short loc_180071F61
0x180071f71  mov     rax, rbx
0x180071f74  mov     edi, 7FFFFFFEh
0x180071f79  sub     rax, rcx
0x180071f7c  test    rcx, rcx
0x180071f7f  cmovz   rax, r12
0x180071f83  jz      short loc_180071FD2
0x180071f85  mov     rdx, rbx
0x180071f88  lea     rcx, [rsp+288h+Name]
0x180071f8d  lea     rcx, [rcx+rax*2]
0x180071f91  sub     rdx, rax
0x180071f94  jz      short loc_180071FC3
0x180071f96  lea     r9, aP0; "_p0"
0x180071f9d  mov     eax, edi
0x180071f9f  sub     r9, rcx
0x180071fa2  test    rax, rax
0x180071fa5  jz      short loc_180071FC3
0x180071fa7  movzx   r8d, word ptr [r9+rcx]
0x180071fac  test    r8w, r8w
0x180071fb0  jz      short loc_180071FC3
0x180071fb2  mov     [rcx], r8w
0x180071fb6  dec     rax
0x180071fb9  add     rcx, 2
0x180071fbd  sub     rdx, 1
0x180071fc1  jnz     short loc_180071FA2
0x180071fc3  test    rdx, rdx
0x180071fc6  lea     rax, [rcx-2]
0x180071fca  cmovnz  rax, rcx
0x180071fce  mov     [rax], r12w
0x180071fd2  mov     rbp, r11
0x180071fd5  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180071fdd  shr     rbp, 1Fh
0x180071fe1  lea     r9, [rsp+288h+Name]; lpName
0x180071fe6  and     r11d, 7FFFFFFFh
0x180071fed  mov     [rsp+288h+dwFlags], r12d; int
0x180071ff2  mov     r14d, 1
0x180071ff8  mov     edx, r11d; lInitialCount
0x180071ffb  mov     r8d, r14d
0x180071ffe  cmova   r8d, r11d; lMaximumCount
0x180072002  xor     ecx, ecx; lpSemaphoreAttributes
0x180072004  call    cs:__imp_CreateSemaphoreExW
0x18007200a  mov     rsi, rax
0x18007200d  test    rax, rax
0x180072010  jnz     short loc_18007205B
0x180072012  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180072017  mov     esi, eax
0x180072019  test    eax, eax
0x18007201b  jns     short loc_18007206C
0x18007201d  lfence
0x180072020  mov     rcx, [rsp+288h]; this
0x180072028  lea     r8, aWil; "wil"
0x18007202f  mov     r9d, eax; char *
0x180072032  mov     edx, 88h; void *
0x180072037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007203c  mov     eax, esi
0x18007203e  jmp     loc_180072151
0x180072043  mov     rax, 0C000000000000000h
0x18007204d  test    rax, r11
0x180072050  jnz     loc_18007219D
0x180072056  jmp     loc_180071EE0
0x18007205b  call    cs:__imp_GetLastError
0x180072061  mov     rdx, rsi
0x180072064  mov     rcx, r13
0x180072067  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007206c  test    r15b, r15b
0x18007206f  jz      loc_18007214F
0x180072075  mov     rcx, rbx
0x180072078  lea     rax, [rsp+288h+Name]
0x18007207d  nop     dword ptr [rax]
0x180072080  cmp     [rax], r12w
0x180072084  jz      short loc_18007208F
0x180072086  add     rax, 2
0x18007208a  sub     rcx, r14
0x18007208d  jnz     short loc_180072080
0x18007208f  mov     rax, rbx
0x180072092  sub     rax, rcx
0x180072095  test    rcx, rcx
0x180072098  cmovz   rax, r12
0x18007209c  jz      short loc_1800720E2
0x18007209e  lea     rcx, [rsp+288h+Name]
0x1800720a3  lea     rcx, [rcx+rax*2]
0x1800720a7  sub     rbx, rax
0x1800720aa  jz      short loc_1800720D3
0x1800720ac  lea     rdx, asc_1802B9360; "h"
0x1800720b3  sub     rdx, rcx
0x1800720b6  test    rdi, rdi
0x1800720b9  jz      short loc_1800720D3
0x1800720bb  movzx   eax, word ptr [rdx+rcx]
0x1800720bf  test    ax, ax
0x1800720c2  jz      short loc_1800720D3
0x1800720c4  mov     [rcx], ax
0x1800720c7  dec     rdi
0x1800720ca  add     rcx, 2
0x1800720ce  sub     rbx, r14
0x1800720d1  jnz     short loc_1800720B6
0x1800720d3  test    rbx, rbx
0x1800720d6  lea     rax, [rcx-2]
0x1800720da  cmovnz  rax, rcx
0x1800720de  mov     [rax], r12w
0x1800720e2  test    ebp, ebp
0x1800720e4  mov     [rsp+288h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800720ec  lea     r9, [rsp+288h+Name]; lpName
0x1800720f1  mov     [rsp+288h+dwFlags], r12d; int
0x1800720f6  cmovnz  r14d, ebp
0x1800720fa  mov     edx, ebp; lInitialCount
0x1800720fc  mov     r8d, r14d; lMaximumCount
0x1800720ff  xor     ecx, ecx; lpSemaphoreAttributes
0x180072101  call    cs:__imp_CreateSemaphoreExW
0x180072107  mov     rbx, rax
0x18007210a  test    rax, rax
0x18007210d  jnz     short loc_18007213D
0x18007210f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180072114  mov     ebx, eax
0x180072116  test    eax, eax
0x180072118  jns     short loc_18007214F
0x18007211a  lfence
0x18007211d  mov     rcx, [rsp+288h]; this
0x180072125  lea     r8, aWil; "wil"
0x18007212c  mov     r9d, eax; char *
0x18007212f  mov     edx, 8Dh; void *
0x180072134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072139  mov     eax, ebx
0x18007213b  jmp     short loc_180072151
0x18007213d  call    cs:__imp_GetLastError
0x180072143  lea     rcx, [r13+8]
0x180072147  mov     rdx, rbx
0x18007214a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007214f  xor     eax, eax
0x180072151  mov     r12, [rsp+288h+var_30]
0x180072159  mov     rdi, [rsp+288h+var_28]
0x180072161  mov     rsi, [rsp+288h+var_20]
0x180072169  mov     rbp, [rsp+288h+var_18]
0x180072171  mov     rbx, [rsp+288h+arg_8]
0x180072179  mov     r14, [rsp+288h+var_38]
0x180072181  mov     rcx, [rsp+288h+var_48]
0x180072189  xor     rcx, rsp; StackCookie
0x18007218c  call    __security_check_cookie
0x180072191  add     rsp, 278h
0x180072198  pop     r15
0x18007219a  pop     r13
0x18007219c  retn
0x18007219d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```

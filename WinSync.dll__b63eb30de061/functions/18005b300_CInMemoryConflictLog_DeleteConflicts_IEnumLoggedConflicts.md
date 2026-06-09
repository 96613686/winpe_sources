# CInMemoryConflictLog::DeleteConflicts(IEnumLoggedConflicts *)

- ea: `0x18005b300`
- end: `0x18005b50c`
- name: `?DeleteConflicts@CInMemoryConflictLog@@UEAAJPEAUIEnumLoggedConflicts@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(CInMemoryConflictLog *__hidden this, struct IEnumLoggedConflicts *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18005b300`
- `0x18005c140`
- `0x18005c7a8`
- `0x18005ca38`
- `0x180094010`

## string_xrefs

- `0x18005b33f`: `CInMemoryConflictLog::DeleteConflicts`
- `0x18005b4dd`: `CInMemoryConflictLog::DeleteConflicts`

## pseudocode

```c
__int64 __fastcall CInMemoryConflictLog::DeleteConflicts(CInMemoryConflictLog *this, struct IEnumLoggedConflicts *a2)
{
  PVOID *v4; // rcx
  int v5; // ebx
  CSyncEnumLoggedConflictsBuilder *v6; // rax
  CSyncEnumLoggedConflictsBuilder *v7; // rax
  CSyncEnumLoggedConflictsBuilder *v8; // rdi
  int v9; // r15d
  __int64 v10; // rcx
  __int64 v11; // rax
  int v13; // [rsp+68h] [rbp+38h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_281efc6728e53000f6946f6c95ac80d8_Traceguids,
      "CInMemoryConflictLog::DeleteConflicts");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v5 = -2147024882;
    v6 = (CSyncEnumLoggedConflictsBuilder *)SeAlloc(0x18u);
    if ( v6 )
    {
      v7 = CSyncEnumLoggedConflictsBuilder::CSyncEnumLoggedConflictsBuilder(v6);
      v8 = v7;
      if ( v7 )
      {
        v5 = CSyncEnumLoggedConflictsBuilder::Init(v7);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(struct IEnumLoggedConflicts *))(*(_QWORD *)a2 + 40LL))(a2);
          if ( v5 >= 0 )
          {
            v13 = 0;
            v9 = 0;
            v14 = 0;
            do
            {
              v5 = (*(__int64 (__fastcall **)(struct IEnumLoggedConflicts *, __int64, __int64 *, int *))(*(_QWORD *)a2 + 24LL))(
                     a2,
                     1,
                     &v14,
                     &v13);
              if ( v5 )
                break;
              v5 = HashTable<ILoggedConflict *,unsigned long,DefaultHashTableContext>::RemoveItem(
                     *((_QWORD *)this + 9),
                     &v14);
              if ( v5 >= 0 )
              {
                v10 = v14;
                *((_DWORD *)this + 14) = 1;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              }
              else
              {
                v9 = 1;
                v5 = (*(__int64 (__fastcall **)(CSyncEnumLoggedConflictsBuilder *, __int64))(*(_QWORD *)v8 + 24LL))(
                       v8,
                       v14);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            }
            while ( !v5 );
            if ( v5 == 1 )
            {
              v5 = 0;
              if ( v9 )
              {
                if ( *((_QWORD *)this + 5) )
                {
                  v11 = *(_QWORD *)v8;
                  v15 = 0;
                  v5 = (*(__int64 (__fastcall **)(CSyncEnumLoggedConflictsBuilder *, __int64 *))(v11 + 32))(v8, &v15);
                  if ( v5 >= 0 )
                  {
                    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 24LL))(
                           *((_QWORD *)this + 5),
                           v15);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
                  }
                }
              }
            }
          }
        }
        (*(void (__fastcall **)(CSyncEnumLoggedConflictsBuilder *))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x100) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      14,
      (unsigned int)WPP_281efc6728e53000f6946f6c95ac80d8_Traceguids,
      (unsigned int)"CInMemoryConflictLog::DeleteConflicts",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005b300  mov     [rsp-28h+arg_0], rbx
0x18005b305  push    rbp
0x18005b306  push    rsi
0x18005b307  push    rdi
0x18005b308  push    r14
0x18005b30a  push    r15
0x18005b30c  mov     rbp, rsp
0x18005b30f  sub     rsp, 30h
0x18005b313  mov     rsi, rdx
0x18005b316  mov     r14, rcx
0x18005b319  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b320  lea     r15, WPP_GLOBAL_Control
0x18005b327  cmp     rcx, r15
0x18005b32a  jz      short loc_18005B35E
0x18005b32c  test    dword ptr [rcx+1Ch], 100h
0x18005b333  jz      short loc_18005B35E
0x18005b335  cmp     byte ptr [rcx+19h], 5
0x18005b339  jb      short loc_18005B35E
0x18005b33b  mov     rcx, [rcx+10h]
0x18005b33f  lea     r9, aCinmemoryconfl_7; "CInMemoryConflictLog::DeleteConflicts"
0x18005b346  mov     edx, 0Dh
0x18005b34b  lea     r8, WPP_281efc6728e53000f6946f6c95ac80d8_Traceguids
0x18005b352  call    WPP_SF_s
0x18005b357  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b35e  mov     ebx, 80004003h
0x18005b363  test    rsi, rsi
0x18005b366  jz      loc_18005B4C5
0x18005b36c  mov     ecx, 18h; unsigned __int64
0x18005b371  mov     ebx, 8007000Eh
0x18005b376  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18005b37b  test    rax, rax
0x18005b37e  jz      loc_18005B4BE
0x18005b384  mov     rcx, rax; this
0x18005b387  call    ??0CSyncEnumLoggedConflictsBuilder@@QEAA@XZ; CSyncEnumLoggedConflictsBuilder::CSyncEnumLoggedConflictsBuilder(void)
0x18005b38c  mov     rdi, rax
0x18005b38f  test    rax, rax
0x18005b392  jz      loc_18005B4BE
0x18005b398  mov     rcx, rax; this
0x18005b39b  call    ?Init@CSyncEnumLoggedConflictsBuilder@@QEAAJXZ; CSyncEnumLoggedConflictsBuilder::Init(void)
0x18005b3a0  mov     ebx, eax
0x18005b3a2  test    eax, eax
0x18005b3a4  js      loc_18005B4AF
0x18005b3aa  mov     rax, [rsi]
0x18005b3ad  mov     rcx, rsi
0x18005b3b0  mov     rax, [rax+28h]
0x18005b3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3b9  mov     ebx, eax
0x18005b3bb  test    eax, eax
0x18005b3bd  js      loc_18005B4AF
0x18005b3c3  mov     [rbp+arg_8], 0
0x18005b3ca  xor     r15d, r15d
0x18005b3cd  mov     [rbp+arg_10], 0
0x18005b3d5  mov     rax, [rsi]
0x18005b3d8  lea     r9, [rbp+arg_8]
0x18005b3dc  lea     r8, [rbp+arg_10]
0x18005b3e0  mov     edx, 1
0x18005b3e5  mov     rcx, rsi
0x18005b3e8  mov     rax, [rax+18h]
0x18005b3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3f1  mov     ebx, eax
0x18005b3f3  test    eax, eax
0x18005b3f5  jnz     short loc_18005B453
0x18005b3f7  mov     rcx, [r14+48h]
0x18005b3fb  lea     rdx, [rbp+arg_10]
0x18005b3ff  call    ?RemoveItem@?$HashTable@PEAUILoggedConflict@@KVDefaultHashTableContext@@@@QEAAJAEBQEAUILoggedConflict@@@Z; HashTable<ILoggedConflict *,ulong,DefaultHashTableContext>::RemoveItem(ILoggedConflict * const &)
0x18005b404  mov     ebx, eax
0x18005b406  test    eax, eax
0x18005b408  jns     short loc_18005B427
0x18005b40a  mov     rax, [rdi]
0x18005b40d  mov     rcx, rdi
0x18005b410  mov     rdx, [rbp+arg_10]
0x18005b414  mov     r15d, 1
0x18005b41a  mov     rax, [rax+18h]
0x18005b41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b423  mov     ebx, eax
0x18005b425  jmp     short loc_18005B43F
0x18005b427  mov     rcx, [rbp+arg_10]
0x18005b42b  mov     dword ptr [r14+38h], 1
0x18005b433  mov     rax, [rcx]
0x18005b436  mov     rax, [rax+10h]
0x18005b43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b43f  mov     rcx, [rbp+arg_10]
0x18005b443  mov     rax, [rcx]
0x18005b446  mov     rax, [rax+10h]
0x18005b44a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b44f  test    ebx, ebx
0x18005b451  jz      short loc_18005B3D5
0x18005b453  cmp     ebx, 1
0x18005b456  jnz     short loc_18005B4A8
0x18005b458  xor     ebx, ebx
0x18005b45a  test    r15d, r15d
0x18005b45d  jz      short loc_18005B4A8
0x18005b45f  cmp     [r14+28h], rbx
0x18005b463  jz      short loc_18005B4A8
0x18005b465  mov     rax, [rdi]
0x18005b468  lea     rdx, [rbp+arg_18]
0x18005b46c  mov     rcx, rdi
0x18005b46f  mov     [rbp+arg_18], rbx
0x18005b473  mov     rax, [rax+20h]
0x18005b477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b47c  mov     ebx, eax
0x18005b47e  test    eax, eax
0x18005b480  js      short loc_18005B4A8
0x18005b482  mov     rcx, [r14+28h]
0x18005b486  mov     rdx, [rbp+arg_18]
0x18005b48a  mov     rax, [rcx]
0x18005b48d  mov     rax, [rax+18h]
0x18005b491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b496  mov     rcx, [rbp+arg_18]
0x18005b49a  mov     ebx, eax
0x18005b49c  mov     rax, [rcx]
0x18005b49f  mov     rax, [rax+10h]
0x18005b4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4a8  lea     r15, WPP_GLOBAL_Control
0x18005b4af  mov     rax, [rdi]
0x18005b4b2  mov     rcx, rdi
0x18005b4b5  mov     rax, [rax+10h]
0x18005b4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b4c5  cmp     rcx, r15
0x18005b4c8  jz      short loc_18005B4F9
0x18005b4ca  test    dword ptr [rcx+1Ch], 100h
0x18005b4d1  jz      short loc_18005B4F9
0x18005b4d3  cmp     byte ptr [rcx+19h], 5
0x18005b4d7  jb      short loc_18005B4F9
0x18005b4d9  mov     rcx, [rcx+10h]
0x18005b4dd  lea     r9, aCinmemoryconfl_7; "CInMemoryConflictLog::DeleteConflicts"
0x18005b4e4  mov     edx, 0Eh
0x18005b4e9  mov     [rsp+30h+var_10], ebx
0x18005b4ed  lea     r8, WPP_281efc6728e53000f6946f6c95ac80d8_Traceguids
0x18005b4f4  call    WPP_SF_sD
0x18005b4f9  mov     eax, ebx
0x18005b4fb  mov     rbx, [rsp+30h+arg_0]
0x18005b500  add     rsp, 30h
0x18005b504  pop     r15
0x18005b506  pop     r14
0x18005b508  pop     rdi
0x18005b509  pop     rsi
0x18005b50a  pop     rbp
0x18005b50b  retn
```

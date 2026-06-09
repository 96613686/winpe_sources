# ESESession::_InitAllTables(void)

- ea: `0x180018f58`
- end: `0x180019045`
- name: `?_InitAllTables@ESESession@@AEAAJXZ`
- size: `237`
- prototype: `__int64 __fastcall(ESESession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180018e18`

## callees

- `0x180002da8`
- `0x180016860`
- `0x180017d74`
- `0x180018778`
- `0x180018f58`

## string_xrefs

- `0x180018f9a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`
- `0x180019011`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\esesession.cpp`

## pseudocode

```c
__int64 __fastcall ESESession::_InitAllTables(ESESession *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rbx
  unsigned int i; // esi
  __int64 v6; // rax
  __int64 v7; // r15
  int Table; // eax
  int v9; // ebp
  __int64 v11; // [rsp+30h] [rbp-58h] BYREF
  int v12; // [rsp+38h] [rbp-50h]
  char *v13; // [rsp+40h] [rbp-48h]

  v11 = *((_QWORD *)this + 7);
  v13 = (char *)this + 64;
  v12 = 0;
  v2 = auto_SessionContext::SetContext((auto_SessionContext *)&v11);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = 0;
LABEL_4:
    if ( (_DWORD)v4 )
    {
      v3 = 0;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= *((_DWORD *)&gc_tableDefinitionMappings + 6 * v4 + 4) )
        {
          v4 = 1;
          goto LABEL_4;
        }
        v6 = *((_QWORD *)&gc_tableDefinitionMappings + 3 * v4 + 1);
        v7 = *(int *)(v6 + 208LL * i + 200);
        Table = ESESession::_CreateTable((__int64)this, *(_DWORD *)(v6 + 208LL * i + 200));
        v9 = Table;
        if ( Table < 0 )
          break;
        *((_DWORD *)this + 12 * v7 + 36) = 0;
      }
      Log_HREvent(
        (unsigned int)Table,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
        828);
      v3 = v9;
    }
  }
  else
  {
    Log_HREvent(
      (unsigned int)v2,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\esesession.cpp",
      814);
  }
  auto_SessionContext::~auto_SessionContext((auto_SessionContext *)&v11);
  return v3;
}

```

## disassembly

```asm
0x180018f58  push    rbx
0x180018f5a  push    rbp
0x180018f5b  push    rsi
0x180018f5c  push    rdi
0x180018f5d  push    r12
0x180018f5f  push    r14
0x180018f61  push    r15
0x180018f63  sub     rsp, 50h
0x180018f67  mov     rax, [rcx+38h]
0x180018f6b  mov     rdi, rcx
0x180018f6e  mov     [rsp+88h+var_58], rax
0x180018f73  lea     rax, [rcx+40h]
0x180018f77  lea     rcx, [rsp+88h+var_58]; this
0x180018f7c  mov     [rsp+88h+var_48], rax
0x180018f81  mov     [rsp+88h+var_50], 0
0x180018f89  call    ?SetContext@auto_SessionContext@@QEAAJXZ; auto_SessionContext::SetContext(void)
0x180018f8e  mov     ebx, eax
0x180018f90  test    eax, eax
0x180018f92  jns     short loc_180018FAF
0x180018f94  mov     r9d, 32Eh
0x180018f9a  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180018fa1  mov     edx, 1
0x180018fa6  mov     ecx, eax
0x180018fa8  call    Log_HREvent
0x180018fad  jmp     short loc_18001902A
0x180018faf  xor     ebx, ebx
0x180018fb1  lea     r12, ?gc_tableDefinitionMappings@@3QBUIndexTableMapping@@B; IndexTableMapping const near * const gc_tableDefinitionMappings
0x180018fb8  cmp     ebx, 1
0x180018fbb  jnb     short loc_180019028
0x180018fbd  xor     esi, esi
0x180018fbf  lea     r14, [rbx+rbx*2]
0x180018fc3  cmp     esi, [r12+r14*8+10h]
0x180018fc8  jnb     short loc_180019007
0x180018fca  mov     eax, esi
0x180018fcc  imul    rcx, rax, 0D0h
0x180018fd3  mov     rax, [r12+r14*8+8]
0x180018fd8  movsxd  r15, dword ptr [rax+rcx+0C8h]
0x180018fe0  mov     rcx, rdi
0x180018fe3  mov     edx, r15d
0x180018fe6  call    ?_CreateTable@ESESession@@AEAAJW4_INDEXTABLE_ID@@@Z; ESESession::_CreateTable(_INDEXTABLE_ID)
0x180018feb  mov     ebp, eax
0x180018fed  test    eax, eax
0x180018fef  js      short loc_18001900B
0x180018ff1  lea     rax, [r15+3]
0x180018ff5  lea     rax, [rax+rax*2]
0x180018ff9  add     rax, rax
0x180018ffc  inc     esi
0x180018ffe  mov     dword ptr [rdi+rax*8], 0
0x180019005  jmp     short loc_180018FC3
0x180019007  inc     ebx
0x180019009  jmp     short loc_180018FB8
0x18001900b  mov     r9d, 33Ch
0x180019011  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180019018  mov     edx, 1
0x18001901d  mov     ecx, ebp
0x18001901f  call    Log_HREvent
0x180019024  mov     ebx, ebp
0x180019026  jmp     short loc_18001902A
0x180019028  xor     ebx, ebx
0x18001902a  lea     rcx, [rsp+88h+var_58]; this
0x18001902f  call    ??1auto_SessionContext@@QEAA@XZ; auto_SessionContext::~auto_SessionContext(void)
0x180019034  mov     eax, ebx
0x180019036  add     rsp, 50h
0x18001903a  pop     r15
0x18001903c  pop     r14
0x18001903e  pop     r12
0x180019040  pop     rdi
0x180019041  pop     rsi
0x180019042  pop     rbp
0x180019043  pop     rbx
0x180019044  retn
```

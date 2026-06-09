# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::EnableCounters(Microsoft::Json::Object &)

- ea: `0x180014084`
- end: `0x1800143c2`
- name: `?EnableCounters@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJAEAVObject@Json@4@@Z`
- size: `830`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, struct Microsoft::Json::Object *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011b60`

## callees

- `0x180014084`
- `0x1800152cc`
- `0x18001543c`
- `0x1800477f8`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180014207`
- `KERNEL32!CompareStringOrdinal` at `0x180014233`
- `KERNEL32!CompareStringOrdinal` at `0x18001426a`
- `KERNEL32!CompareStringOrdinal` at `0x180014207`
- `KERNEL32!CompareStringOrdinal` at `0x180014233`
- `KERNEL32!CompareStringOrdinal` at `0x18001426a`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001437c`
- `KERNEL32!ReleaseSRWLockShared` at `0x18001437c`
- `KERNEL32!AcquireSRWLockShared` at `0x1800142e8`
- `KERNEL32!AcquireSRWLockShared` at `0x1800142e8`
- `KERNEL32!LeaveCriticalSection` at `0x18001436a`
- `KERNEL32!LeaveCriticalSection` at `0x18001436a`
- `KERNEL32!EnterCriticalSection` at `0x18001430b`
- `KERNEL32!EnterCriticalSection` at `0x18001430b`
- `OLEAUT32!__imp_SysAllocString` at `0x180014172`
- `OLEAUT32!__imp_SysAllocString` at `0x180014172`
- `OLEAUT32!__imp_SysFreeString` at `0x180014198`
- `OLEAUT32!__imp_SysFreeString` at `0x180014290`
- `OLEAUT32!__imp_SysFreeString` at `0x180014198`
- `OLEAUT32!__imp_SysFreeString` at `0x180014290`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::EnableCounters(
        RTL_SRWLOCK *this,
        struct Microsoft::Json::Object *a2)
{
  signed int FieldAsArray; // esi
  volatile signed __int32 *v4; // rbx
  __int64 result; // rax
  __int64 v6; // r14
  __int64 v7; // r15
  OLECHAR *v8; // rbx
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rbx
  _QWORD *Ptr; // r15
  _QWORD *i; // rdi
  __int64 v14; // r14
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  unsigned int *j; // rcx
  char *v17; // r8
  _QWORD *v18; // rdx
  __int64 v19; // r9
  char v20; // al
  __int64 v21; // rax
  __int128 v22; // [rsp+30h] [rbp-68h] BYREF
  __int64 v23; // [rsp+40h] [rbp-58h]
  __int128 v24; // [rsp+48h] [rbp-50h] BYREF
  OLECHAR *v25; // [rsp+58h] [rbp-40h]
  _DWORD v26[2]; // [rsp+60h] [rbp-38h] BYREF

  try
  {
    v22 = 0;
    v23 = 0;
    v24 = 0;
    FieldAsArray = Microsoft::Json::Object::GetFieldAsArray(a2, L"counters", &v24);
    if ( FieldAsArray < 0 )
    {
      _mm_lfence();
      v4 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
      if ( *((_QWORD *)&v24 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
          if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        }
      }
LABEL_7:
      std::vector<unsigned int>::_Tidy(&v22);
      return (unsigned int)FieldAsArray;
    }
    v6 = 0;
    v7 = v24;
    while ( 1 )
    {
      if ( (unsigned int)v6 >= *(_DWORD *)(*(_QWORD *)v7 + 8LL) )
      {
        v11 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
        if ( *((_QWORD *)&v24 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        AcquireSRWLockShared(this + 20);
        Ptr = this[23].Ptr;
        for ( i = this[22].Ptr; i != Ptr; ++i )
        {
          v14 = *i;
          v15 = (struct _RTL_CRITICAL_SECTION *)(*i + 144LL);
          EnterCriticalSection(v15);
          v26[0] = 0;
          for ( j = (unsigned int *)v22; j != *((unsigned int **)&v22 + 1); ++j )
            *((_BYTE *)v26 + *j) = 1;
          v17 = (char *)v26;
          v18 = (_QWORD *)(v14 + 200);
          v19 = 4;
          do
          {
            v20 = *v17;
            *((_BYTE *)v18 - 16) = *v17;
            if ( !v20 )
            {
              v21 = *(v18 - 1);
              if ( v21 != *v18 )
                *v18 = v21;
            }
            ++v17;
            v18 += 9;
            --v19;
          }
          while ( v19 );
          LeaveCriticalSection(v15);
        }
        ReleaseSRWLockShared(this + 20);
        std::vector<unsigned int>::_Tidy(&v22);
        return 0;
      }
      v8 = 0;
      v9 = **(_QWORD **)v7 + 24 * v6;
      if ( (*(_DWORD *)(v9 + 16) & 0x100000) == 0 )
      {
        FieldAsArray = -2147024809;
LABEL_15:
        _mm_lfence();
        SysFreeString(v8);
        v10 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
        if ( *((_QWORD *)&v24 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          }
        }
        goto LABEL_7;
      }
      if ( (*(_DWORD *)(v9 + 16) & 0x400000) == 0 )
        v9 = *(_QWORD *)v9;
      v8 = SysAllocString((const OLECHAR *)v9);
      v25 = v8;
      FieldAsArray = v8 == 0 ? 0x8007000E : 0;
      if ( !v8 )
        goto LABEL_15;
      if ( CompareStringOrdinal(v8, -1, L"DiagnosticsHub.Counters.Process.PrivateBytes", -1, 0) == 2 )
        break;
      if ( CompareStringOrdinal(v8, -1, L"DiagnosticsHub.Counters.Process.CPU", -1, 0) == 2 )
      {
        v26[0] = 2;
        goto LABEL_24;
      }
      if ( CompareStringOrdinal(v8, -1, L"DiagnosticsHub.Counters.Process.Time", -1, 0) == 2 )
      {
        v26[0] = 3;
        std::vector<enum Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType>::push_back(&v22, v26);
      }
LABEL_27:
      SysFreeString(v8);
      v6 = (unsigned int)(v6 + 1);
    }
    v26[0] = 1;
LABEL_24:
    std::vector<enum Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType>::push_back(&v22, v26);
    goto LABEL_27;
  }
  catch ( std::bad_alloc )
  {
    std::vector<unsigned int>::_Tidy(&v22);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014084  mov     [rsp+arg_10], rbx
0x180014089  push    rsi
0x18001408a  push    rdi
0x18001408b  push    r13
0x18001408d  push    r14
0x18001408f  push    r15
0x180014091  sub     rsp, 70h
0x180014095  mov     rax, cs:__security_cookie
0x18001409c  xor     rax, rsp
0x18001409f  mov     [rsp+98h+var_30], rax
0x1800140a4  mov     rax, rdx
0x1800140a7  mov     r13, rcx
0x1800140aa  xor     ecx, ecx
0x1800140ac  xorps   xmm1, xmm1
0x1800140af  movdqu  [rsp+98h+var_68], xmm1
0x1800140b5  mov     [rsp+98h+var_58], rcx
0x1800140ba  movdqu  [rsp+98h+var_50], xmm1
0x1800140c0  lea     r8, [rsp+98h+var_50]
0x1800140c5  lea     rdx, aCounters_0; "counters"
0x1800140cc  mov     rcx, rax
0x1800140cf  call    ?GetFieldAsArray@Object@Json@Microsoft@@QEAAJPEBGAEAV?$shared_ptr@VArray@Json@Microsoft@@@std@@@Z; Microsoft::Json::Object::GetFieldAsArray(ushort const *,std::shared_ptr<Microsoft::Json::Array> &)
0x1800140d4  mov     esi, eax
0x1800140d6  test    eax, eax
0x1800140d8  jns     short loc_180014131
0x1800140da  lfence
0x1800140dd  mov     rbx, qword ptr [rsp+98h+var_50+8]
0x1800140e2  test    rbx, rbx
0x1800140e5  jz      short loc_180014120
0x1800140e7  or      edi, 0FFFFFFFFh
0x1800140ea  mov     ecx, edi
0x1800140ec  lock xadd [rbx+8], ecx
0x1800140f1  add     ecx, edi
0x1800140f3  jnz     short loc_180014120
0x1800140f5  mov     rax, [rbx]
0x1800140f8  mov     rcx, rbx
0x1800140fb  mov     rax, [rax]
0x1800140fe  call    cs:__guard_dispatch_icall_fptr
0x180014104  mov     eax, edi
0x180014106  lock xadd [rbx+0Ch], eax
0x18001410b  add     eax, edi
0x18001410d  jnz     short loc_180014120
0x18001410f  mov     rax, [rbx]
0x180014112  mov     rcx, rbx
0x180014115  mov     rax, [rax+8]
0x180014119  call    cs:__guard_dispatch_icall_fptr
0x18001411f  nop
0x180014120  lea     rcx, [rsp+98h+var_68]
0x180014125  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18001412a  mov     eax, esi
0x18001412c  jmp     loc_1800143A0
0x180014131  xor     r14d, r14d
0x180014134  or      edi, 0FFFFFFFFh
0x180014137  mov     r15, qword ptr [rsp+98h+var_50]
0x18001413c  mov     rdx, [r15]
0x18001413f  cmp     r14d, [rdx+8]
0x180014143  jnb     loc_18001429E
0x180014149  xor     ebx, ebx
0x18001414b  lea     rcx, [r14+r14*2]
0x18001414f  mov     rax, [rdx]
0x180014152  lea     rcx, [rax+rcx*8]
0x180014156  test    dword ptr [rcx+10h], 100000h
0x18001415d  jnz     short loc_180014166
0x18001415f  mov     esi, 80070057h
0x180014164  jmp     short loc_180014192
0x180014166  test    dword ptr [rcx+10h], 400000h
0x18001416d  jnz     short loc_180014172
0x18001416f  mov     rcx, [rcx]; psz
0x180014172  call    cs:__imp_SysAllocString
0x180014178  mov     rbx, rax
0x18001417b  mov     [rsp+98h+var_40], rax
0x180014180  neg     rax
0x180014183  sbb     esi, esi
0x180014185  not     esi
0x180014187  and     esi, 8007000Eh
0x18001418d  test    rbx, rbx
0x180014190  jnz     short loc_1800141F0
0x180014192  lfence
0x180014195  mov     rcx, rbx; bstrString
0x180014198  call    cs:__imp_SysFreeString
0x18001419e  nop
0x18001419f  mov     rbx, qword ptr [rsp+98h+var_50+8]
0x1800141a4  test    rbx, rbx
0x1800141a7  jz      short loc_1800141DF
0x1800141a9  mov     eax, edi
0x1800141ab  lock xadd [rbx+8], eax
0x1800141b0  add     eax, edi
0x1800141b2  jnz     short loc_1800141DF
0x1800141b4  mov     rax, [rbx]
0x1800141b7  mov     rcx, rbx
0x1800141ba  mov     rax, [rax]
0x1800141bd  call    cs:__guard_dispatch_icall_fptr
0x1800141c3  mov     eax, edi
0x1800141c5  lock xadd [rbx+0Ch], eax
0x1800141ca  add     eax, edi
0x1800141cc  jnz     short loc_1800141DF
0x1800141ce  mov     rdx, [rbx]
0x1800141d1  mov     rcx, rbx
0x1800141d4  mov     rax, [rdx+8]
0x1800141d8  call    cs:__guard_dispatch_icall_fptr
0x1800141de  nop
0x1800141df  lea     rcx, [rsp+98h+var_68]
0x1800141e4  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x1800141e9  mov     eax, esi
0x1800141eb  jmp     loc_1800143A0
0x1800141f0  mov     [rsp+98h+bIgnoreCase], 0; bIgnoreCase
0x1800141f8  mov     r9d, edi; cchCount2
0x1800141fb  lea     r8, aDiagnosticshub_9; "DiagnosticsHub.Counters.Process.Private"...
0x180014202  mov     edx, edi; cchCount1
0x180014204  mov     rcx, rbx; lpString1
0x180014207  call    cs:__imp_CompareStringOrdinal
0x18001420d  cmp     eax, 2
0x180014210  jnz     short loc_18001421C
0x180014212  mov     [rsp+98h+var_38], 1
0x18001421a  jmp     short loc_180014242
0x18001421c  mov     [rsp+98h+bIgnoreCase], 0; bIgnoreCase
0x180014224  mov     r9d, edi; cchCount2
0x180014227  lea     r8, aDiagnosticshub_10; "DiagnosticsHub.Counters.Process.CPU"
0x18001422e  mov     edx, edi; cchCount1
0x180014230  mov     rcx, rbx; lpString1
0x180014233  call    cs:__imp_CompareStringOrdinal
0x180014239  cmp     eax, 2
0x18001423c  jnz     short loc_180014253
0x18001423e  mov     [rsp+98h+var_38], eax
0x180014242  lea     rdx, [rsp+98h+var_38]
0x180014247  lea     rcx, [rsp+98h+var_68]
0x18001424c  call    ?push_back@?$vector@W4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@V?$allocator@W4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@@std@@@std@@QEAAX$$QEAW4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@@Z; std::vector<Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType>::push_back(Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType &&)
0x180014251  jmp     short loc_18001428D
0x180014253  mov     [rsp+98h+bIgnoreCase], 0; bIgnoreCase
0x18001425b  mov     r9d, edi; cchCount2
0x18001425e  lea     r8, aDiagnosticshub_11; "DiagnosticsHub.Counters.Process.Time"
0x180014265  mov     edx, edi; cchCount1
0x180014267  mov     rcx, rbx; lpString1
0x18001426a  call    cs:__imp_CompareStringOrdinal
0x180014270  cmp     eax, 2
0x180014273  jnz     short loc_18001428D
0x180014275  mov     [rsp+98h+var_38], 3
0x18001427d  lea     rdx, [rsp+98h+var_38]
0x180014282  lea     rcx, [rsp+98h+var_68]
0x180014287  call    ?push_back@?$vector@W4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@V?$allocator@W4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@@std@@@std@@QEAAX$$QEAW4ProcessCounterType@EtwProvider@DiagnosticsHub@Microsoft@@@Z; std::vector<Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType>::push_back(Microsoft::DiagnosticsHub::EtwProvider::ProcessCounterType &&)
0x18001428c  nop
0x18001428d  mov     rcx, rbx; bstrString
0x180014290  call    cs:__imp_SysFreeString
0x180014296  inc     r14d
0x180014299  jmp     loc_18001413C
0x18001429e  mov     rbx, qword ptr [rsp+98h+var_50+8]
0x1800142a3  test    rbx, rbx
0x1800142a6  jz      short loc_1800142DE
0x1800142a8  mov     eax, edi
0x1800142aa  lock xadd [rbx+8], eax
0x1800142af  add     eax, edi
0x1800142b1  jnz     short loc_1800142DE
0x1800142b3  mov     rax, [rbx]
0x1800142b6  mov     rcx, rbx
0x1800142b9  mov     rax, [rax]
0x1800142bc  call    cs:__guard_dispatch_icall_fptr
0x1800142c2  mov     eax, edi
0x1800142c4  lock xadd [rbx+0Ch], eax
0x1800142c9  add     eax, edi
0x1800142cb  jnz     short loc_1800142DE
0x1800142cd  mov     rax, [rbx]
0x1800142d0  mov     rcx, rbx
0x1800142d3  mov     rax, [rax+8]
0x1800142d7  call    cs:__guard_dispatch_icall_fptr
0x1800142dd  nop
0x1800142de  lea     rsi, [r13+0A0h]
0x1800142e5  mov     rcx, rsi; SRWLock
0x1800142e8  call    cs:__imp_AcquireSRWLockShared
0x1800142ee  mov     r15, [r13+0B8h]
0x1800142f5  mov     rdi, [r13+0B0h]
0x1800142fc  jmp     short loc_180014374
0x1800142fe  mov     r14, [rdi]
0x180014301  lea     rbx, [r14+90h]
0x180014308  mov     rcx, rbx; lpCriticalSection
0x18001430b  call    cs:__imp_EnterCriticalSection
0x180014311  mov     [rsp+98h+var_38], 0
0x180014319  mov     rcx, qword ptr [rsp+98h+var_68]
0x18001431e  jmp     short loc_18001432B
0x180014320  mov     eax, [rcx]
0x180014322  mov     byte ptr [rsp+rax+98h+var_38], 1
0x180014327  add     rcx, 4
0x18001432b  cmp     rcx, qword ptr [rsp+98h+var_68+8]
0x180014330  jnz     short loc_180014320
0x180014332  lea     r8, [rsp+98h+var_38]
0x180014337  lea     rdx, [r14+0C8h]
0x18001433e  mov     r9d, 4
0x180014344  mov     al, [r8]
0x180014347  mov     [rdx-10h], al
0x18001434a  test    al, al
0x18001434c  jnz     short loc_18001435A
0x18001434e  mov     rax, [rdx-8]
0x180014352  cmp     rax, [rdx]
0x180014355  jz      short loc_18001435A
0x180014357  mov     [rdx], rax
0x18001435a  inc     r8
0x18001435d  add     rdx, 48h ; 'H'
0x180014361  sub     r9, 1
0x180014365  jnz     short loc_180014344
0x180014367  mov     rcx, rbx; lpCriticalSection
0x18001436a  call    cs:__imp_LeaveCriticalSection
0x180014370  add     rdi, 8
0x180014374  cmp     rdi, r15
0x180014377  jnz     short loc_1800142FE
0x180014379  mov     rcx, rsi; SRWLock
0x18001437c  call    cs:__imp_ReleaseSRWLockShared
0x180014382  nop
0x180014383  lea     rcx, [rsp+98h+var_68]
0x180014388  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18001438d  xor     eax, eax
0x18001438f  jmp     short loc_1800143A0
0x180014391  lea     rcx, [rsp+98h+var_68]
0x180014396  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x18001439b  mov     eax, 8007000Eh
0x1800143a0  mov     rcx, [rsp+98h+var_30]
0x1800143a5  xor     rcx, rsp; StackCookie
0x1800143a8  call    __security_check_cookie
0x1800143ad  mov     rbx, [rsp+98h+arg_10]
0x1800143b5  add     rsp, 70h
0x1800143b9  pop     r15
0x1800143bb  pop     r14
0x1800143bd  pop     r13
0x1800143bf  pop     rdi
0x1800143c0  pop     rsi
0x1800143c1  retn
```

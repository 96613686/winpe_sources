# CConflict::Write(void)

- ea: `0x18000c8c0`
- end: `0x18000ca37`
- name: `?Write@CConflict@@UEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(CConflict *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180009584`
- `0x18000c8c0`
- `0x18001b1a0`
- `0x180029cc0`
- `0x180029eb4`
- `0x180029fd0`

## pseudocode

```c
__int64 __fastcall CConflict::Write(CConflict *this)
{
  int v2; // eax
  const unsigned __int16 *v3; // r8
  int v4; // r8d
  int v5; // eax
  CAppInfo **v6; // rdi
  int v7; // eax

  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4, 0xC25u, *(_QWORD *)(*((_QWORD *)this + 5) + 40LL), *(_QWORD *)(*((_QWORD *)this + 5) + 72LL));
  v2 = CGroupPolicyRecord::SetValue(this, L"id", *((const unsigned __int16 **)this + 6));
  if ( v2 >= 0 )
  {
    v2 = CGroupPolicyRecord::SetValue(this, L"precedence", *((_DWORD *)this + 14));
    if ( v2 < 0 )
    {
      if ( !*(_DWORD *)&gDebugLevel )
        return 0;
      v3 = L"precedence";
      goto LABEL_6;
    }
    if ( *((_DWORD *)this + 14) == 1 )
      *((_DWORD *)this + 15) = 5;
    v4 = *((_DWORD *)this + 15);
    if ( v4 )
    {
      v5 = CGroupPolicyRecord::SetValue(this, L"PrecedenceReason", v4);
      if ( v5 < 0 )
      {
        if ( *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC29u, L"PrecedenceReason", (unsigned int)v5);
      }
    }
    if ( *((_DWORD *)this + 14) )
    {
      if ( *((int *)this + 14) <= 1 && *((_DWORD *)this + 4) )
      {
        v6 = (CAppInfo **)((char *)this + 40);
      }
      else
      {
        v6 = (CAppInfo **)((char *)this + 40);
        *(_DWORD *)(*((_QWORD *)this + 5) + 380LL) = 0;
        v7 = CGroupPolicyRecord::ClearValue(this, L"ApplyCause");
        if ( v7 < 0 && *(_DWORD *)&gDebugLevel )
          _DebugMsg(4, 0xC29u, L"ApplyCause", (unsigned int)v7);
      }
    }
    else
    {
      v6 = (CAppInfo **)((char *)this + 40);
      *(_DWORD *)(*((_QWORD *)this + 5) + 384LL) = 1;
    }
    CAppInfo::Write(*v6, this);
  }
  else if ( *(_DWORD *)&gDebugLevel )
  {
    v3 = L"id";
LABEL_6:
    _DebugMsg(4, 0xC29u, v3, (unsigned int)v2);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c8c0  mov     [rsp+arg_0], rbx
0x18000c8c5  mov     [rsp+arg_8], rbp
0x18000c8ca  push    rdi
0x18000c8cb  sub     rsp, 20h
0x18000c8cf  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c8d6  mov     rbx, rcx
0x18000c8d9  mov     ebp, 4
0x18000c8de  jz      short loc_18000C8F8
0x18000c8e0  mov     r8, [rcx+28h]
0x18000c8e4  mov     edx, 0C25h; unsigned int
0x18000c8e9  mov     ecx, ebp; unsigned int
0x18000c8eb  mov     r9, [r8+48h]
0x18000c8ef  mov     r8, [r8+28h]
0x18000c8f3  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000c8f8  mov     r8, [rbx+30h]; unsigned __int16 *
0x18000c8fc  lea     rdx, aId; "id"
0x18000c903  mov     rcx, rbx; this
0x18000c906  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBG0@Z; CGroupPolicyRecord::SetValue(ushort const *,ushort const *)
0x18000c90b  test    eax, eax
0x18000c90d  jns     short loc_18000C937
0x18000c90f  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c916  jz      loc_18000CA25
0x18000c91c  lea     r8, aId; "id"
0x18000c923  mov     r9d, eax
0x18000c926  mov     edx, 0C29h; unsigned int
0x18000c92b  mov     ecx, ebp; unsigned int
0x18000c92d  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000c932  jmp     loc_18000CA25
0x18000c937  mov     r8d, [rbx+38h]; int
0x18000c93b  lea     rdx, aPrecedence; "precedence"
0x18000c942  mov     rcx, rbx; this
0x18000c945  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000c94a  test    eax, eax
0x18000c94c  jns     short loc_18000C964
0x18000c94e  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c955  jz      loc_18000CA25
0x18000c95b  lea     r8, aPrecedence; "precedence"
0x18000c962  jmp     short loc_18000C923
0x18000c964  cmp     dword ptr [rbx+38h], 1
0x18000c968  jnz     short loc_18000C971
0x18000c96a  mov     dword ptr [rbx+3Ch], 5
0x18000c971  mov     r8d, [rbx+3Ch]; int
0x18000c975  test    r8d, r8d
0x18000c978  jz      short loc_18000C9AC
0x18000c97a  lea     rdx, aPrecedencereas; "PrecedenceReason"
0x18000c981  mov     rcx, rbx; this
0x18000c984  call    ?SetValue@CGroupPolicyRecord@@QEAAJPEBGJ@Z; CGroupPolicyRecord::SetValue(ushort const *,long)
0x18000c989  test    eax, eax
0x18000c98b  jns     short loc_18000C9AC
0x18000c98d  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c994  jz      short loc_18000C9AC
0x18000c996  mov     r9d, eax
0x18000c999  lea     r8, aPrecedencereas; "PrecedenceReason"
0x18000c9a0  mov     edx, 0C29h; unsigned int
0x18000c9a5  mov     ecx, ebp; unsigned int
0x18000c9a7  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000c9ac  cmp     dword ptr [rbx+38h], 0
0x18000c9b0  jz      short loc_18000CA09
0x18000c9b2  cmp     dword ptr [rbx+38h], 1
0x18000c9b6  jg      short loc_18000C9C4
0x18000c9b8  cmp     dword ptr [rbx+10h], 0
0x18000c9bc  jz      short loc_18000C9C4
0x18000c9be  lea     rdi, [rbx+28h]
0x18000c9c2  jmp     short loc_18000CA1A
0x18000c9c4  lea     rdi, [rbx+28h]
0x18000c9c8  mov     rcx, rbx; this
0x18000c9cb  mov     rax, [rdi]
0x18000c9ce  lea     rdx, aApplycause; "ApplyCause"
0x18000c9d5  mov     dword ptr [rax+17Ch], 0
0x18000c9df  call    ?ClearValue@CGroupPolicyRecord@@QEAAJPEBG@Z; CGroupPolicyRecord::ClearValue(ushort const *)
0x18000c9e4  test    eax, eax
0x18000c9e6  jns     short loc_18000CA1A
0x18000c9e8  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18000c9ef  jz      short loc_18000CA1A
0x18000c9f1  mov     r9d, eax
0x18000c9f4  lea     r8, aApplycause; "ApplyCause"
0x18000c9fb  mov     edx, 0C29h; unsigned int
0x18000ca00  mov     ecx, ebp; unsigned int
0x18000ca02  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18000ca07  jmp     short loc_18000CA1A
0x18000ca09  lea     rdi, [rbx+28h]
0x18000ca0d  mov     rax, [rdi]
0x18000ca10  mov     dword ptr [rax+180h], 1
0x18000ca1a  mov     rcx, [rdi]; this
0x18000ca1d  mov     rdx, rbx; struct CGroupPolicyRecord *
0x18000ca20  call    ?Write@CAppInfo@@QEAAJPEAVCGroupPolicyRecord@@@Z; CAppInfo::Write(CGroupPolicyRecord *)
0x18000ca25  mov     rbx, [rsp+28h+arg_0]
0x18000ca2a  xor     eax, eax
0x18000ca2c  mov     rbp, [rsp+28h+arg_8]
0x18000ca31  add     rsp, 20h
0x18000ca35  pop     rdi
0x18000ca36  retn
```

# AppHostConfigPathNavigator::MoveToPath(ushort const *)

- ea: `0x180005390`
- end: `0x180005447`
- name: `?MoveToPath@AppHostConfigPathNavigator@@QEAAJPEBG@Z`
- size: `183`
- prototype: `__int64 __fastcall(AppHostConfigPathNavigator *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000eac0`
- `0x18000ec40`

## callees

- `0x180005390`
- `0x180007344`
- `0x18000c9bc`
- `0x180014010`

## string_xrefs

- `0x1800053b2`: `ConfigPathNodeType_Location`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppHostConfigPathNavigator::MoveToPath(AppHostConfigPathNavigator *this, unsigned __int16 *a2)
{
  __int64 v4; // rdx
  AppHostNameTable *v5; // rdi
  __int64 result; // rax
  const unsigned __int16 **v7; // r9
  unsigned int v8; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+38h] [rbp-20h] BYREF
  const wchar_t *v10; // [rsp+40h] [rbp-18h]
  unsigned __int16 *v11; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = a2;
  try
  {
    v4 = *((_QWORD *)this + 5);
    v9 = 10;
    v10 = L"ConfigPathNodeType_Location";
    ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(v4 + 24, v4, a2, &v9);
    v11 = 0;
    v5 = (AppHostNameTable *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 16LL))(*((_QWORD *)this + 5));
  }
  catch ( long v8 )
  {
    return v8;
  }
  catch ( ... )
  {
    return 2147549183LL;
  }
  while ( AppHostNameTable::TryConsumeAndAtomizeSegment(v5, (const unsigned __int16 **)&v12, 0, v7, &v11) )
  {
    result = (*(__int64 (__fastcall **)(AppHostConfigPathNavigator *, _QWORD, unsigned __int16 *))(*(_QWORD *)this
                                                                                                 + 136LL))(
               this,
               0,
               v11);
    if ( (int)result < 0 )
      return result;
    v11 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180005390  mov     r11, rsp
0x180005393  mov     [r11+18h], rbx
0x180005397  mov     [r11+10h], rdx
0x18000539b  push    rdi
0x18000539c  sub     rsp, 50h
0x1800053a0  mov     r8, rdx
0x1800053a3  mov     rbx, rcx
0x1800053a6  mov     rdx, [rcx+28h]
0x1800053aa  mov     [rsp+58h+var_20], 0Ah
0x1800053b2  lea     rax, aConfigpathnode_6; "ConfigPathNodeType_Location"
0x1800053b9  mov     [r11-18h], rax
0x1800053bd  lea     rcx, [rdx+18h]
0x1800053c1  lea     r9, [r11-20h]
0x1800053c5  call    ?GetOrCreateInstanceAtRelativePath@ConfigPathTagNode@@QEAAPEAV1@PEAVConfigPathNavigationTree@@PEBGAEAV?$NamedEnum@W4ConfigPathNodeType@@@@@Z; ConfigPathTagNode::GetOrCreateInstanceAtRelativePath(ConfigPathNavigationTree *,ushort const *,NamedEnum<ConfigPathNodeType> &)
0x1800053ca  mov     [rsp+58h+arg_0], 0
0x1800053d3  mov     rcx, [rbx+28h]
0x1800053d7  mov     rax, [rcx]
0x1800053da  mov     rax, [rax+10h]
0x1800053de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053e3  mov     rdi, rax
0x1800053e6  lea     rax, [rsp+58h+arg_0]
0x1800053eb  mov     [rsp+58h+var_38], rax; unsigned __int16 **
0x1800053f0  xor     r8d, r8d; unsigned __int16 **
0x1800053f3  lea     rdx, [rsp+58h+arg_8]; unsigned __int16 **
0x1800053f8  mov     rcx, rdi; this
0x1800053fb  call    ?TryConsumeAndAtomizeSegment@AppHostNameTable@@QEAA_NPEAPEBG000@Z; AppHostNameTable::TryConsumeAndAtomizeSegment(ushort const * *,ushort const * *,ushort const * *,ushort const * *)
0x180005400  test    al, al
0x180005402  jz      short loc_18000542C
0x180005404  mov     rax, [rbx]
0x180005407  mov     r8, [rsp+58h+arg_0]
0x18000540c  xor     edx, edx
0x18000540e  mov     rcx, rbx
0x180005411  mov     rax, [rax+88h]
0x180005418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000541d  test    eax, eax
0x18000541f  js      short loc_18000543B
0x180005421  mov     [rsp+58h+arg_0], 0
0x18000542a  jmp     short loc_1800053E6
0x18000542c  xor     eax, eax
0x18000542e  jmp     short loc_18000543B
0x180005430  mov     eax, [rsp+58h+var_28]
0x180005434  jmp     short loc_18000543B
0x180005436  mov     eax, 8000FFFFh
0x18000543b  mov     rbx, [rsp+58h+arg_10]
0x180005440  add     rsp, 50h
0x180005444  pop     rdi
0x180005445  retn
```

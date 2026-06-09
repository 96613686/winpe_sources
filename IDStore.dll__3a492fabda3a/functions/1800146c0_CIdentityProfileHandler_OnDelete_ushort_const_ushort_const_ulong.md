# CIdentityProfileHandler::OnDelete(ushort const *,ushort const *,ulong)

- ea: `0x1800146c0`
- end: `0x18001478f`
- name: `?OnDelete@CIdentityProfileHandler@@UEAAJPEBG0K@Z`
- size: `207`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003560`
- `0x18000acb0`
- `0x18001448c`
- `0x1800145a0`
- `0x1800146c0`
- `0x180015184`

## string_xrefs

- `0x1800146d9`: `CIdentityProfileHandler::OnDelete`

## pseudocode

```c
__int64 __fastcall CIdentityProfileHandler::OnDelete(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HKEY v5; // rdx
  CIdentityProfileHandler *v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // ebx
  _BYTE v10[24]; // [rsp+30h] [rbp-18h] BYREF
  int v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  CLogBlock::CLogBlock((CLogBlock *)v10, "CIdentityProfileHandler::OnDelete", &v11);
  if ( a2 )
  {
    v11 = CIdentityProfileHandler::_RemoveRegKey(v6, v5, this[8], a2);
    v8 = v11;
    if ( v11 < 0
      && WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)WPP_0955e053d70b3b28b837838791dca877_Traceguids,
        (_DWORD)a2,
        v11);
      v8 = v11;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0955e053d70b3b28b837838791dca877_Traceguids);
    }
    v8 = -2147024809;
    v11 = -2147024809;
  }
  CLogBlock::~CLogBlock((CLogBlock *)v10, (__int64)v5, v7);
  return v8;
}

```

## disassembly

```asm
0x1800146c0  mov     rax, rsp
0x1800146c3  mov     [rax+8], rbx
0x1800146c7  push    rdi
0x1800146c8  sub     rsp, 40h
0x1800146cc  mov     rdi, rdx
0x1800146cf  mov     dword ptr [rax+10h], 0
0x1800146d6  mov     rbx, rcx
0x1800146d9  lea     rdx, aCidentityprofi_5; "CIdentityProfileHandler::OnDelete"
0x1800146e0  lea     rcx, [rax-18h]; this
0x1800146e4  lea     r8, [rax+10h]; int *
0x1800146e8  call    ??0CLogBlock@@QEAA@PEBDPEAJ@Z; CLogBlock::CLogBlock(char const *,long *)
0x1800146ed  test    rdi, rdi
0x1800146f0  jnz     short loc_180014729
0x1800146f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146f9  lea     rax, WPP_GLOBAL_Control
0x180014700  cmp     rcx, rax
0x180014703  jz      short loc_18001471E
0x180014705  test    byte ptr [rcx+1Ch], 4
0x180014709  jz      short loc_18001471E
0x18001470b  mov     rcx, [rcx+10h]
0x18001470f  lea     edx, [rdi+0Ah]
0x180014712  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180014719  call    WPP_SF_
0x18001471e  mov     ebx, 80070057h
0x180014723  mov     [rsp+48h+arg_8], ebx
0x180014727  jmp     short loc_180014778
0x180014729  mov     r8, [rbx+40h]; unsigned __int16 *
0x18001472d  mov     r9, rdi; unsigned __int16 *
0x180014730  call    ?_RemoveRegKey@CIdentityProfileHandler@@AEAAJPEAUHKEY__@@PEBG1@Z; CIdentityProfileHandler::_RemoveRegKey(HKEY__ *,ushort const *,ushort const *)
0x180014735  mov     [rsp+48h+arg_8], eax
0x180014739  mov     ebx, eax
0x18001473b  test    eax, eax
0x18001473d  jns     short loc_180014778
0x18001473f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014746  lea     rax, WPP_GLOBAL_Control
0x18001474d  cmp     rcx, rax
0x180014750  jz      short loc_180014778
0x180014752  test    byte ptr [rcx+1Ch], 8
0x180014756  jz      short loc_180014778
0x180014758  mov     rcx, [rcx+10h]
0x18001475c  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180014763  mov     edx, 0Bh
0x180014768  mov     [rsp+48h+var_28], ebx
0x18001476c  mov     r9, rdi
0x18001476f  call    WPP_SF_Sd
0x180014774  mov     ebx, [rsp+48h+arg_8]
0x180014778  lea     rcx, [rsp+48h+var_18]; this
0x18001477d  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x180014782  mov     eax, ebx
0x180014784  mov     rbx, [rsp+48h+arg_0]
0x180014789  add     rsp, 40h
0x18001478d  pop     rdi
0x18001478e  retn
```

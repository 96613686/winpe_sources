# CIdentityProfileHandler::OnCreate(ushort const *,ushort const *,ulong)

- ea: `0x180014670`
- end: `0x1800146ac`
- name: `?OnCreate@CIdentityProfileHandler@@UEAAJPEBG0K@Z`
- size: `60`
- prototype: `__int64 __fastcall(CIdentityProfileHandler *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18001448c`
- `0x180014670`

## pseudocode

```c
__int64 __fastcall CIdentityProfileHandler::OnCreate(
        CIdentityProfileHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0955e053d70b3b28b837838791dca877_Traceguids);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x180014670  sub     rsp, 28h
0x180014674  mov     rcx, cs:WPP_GLOBAL_Control
0x18001467b  lea     rax, WPP_GLOBAL_Control
0x180014682  cmp     rcx, rax
0x180014685  jz      short loc_1800146A2
0x180014687  test    byte ptr [rcx+1Ch], 8
0x18001468b  jz      short loc_1800146A2
0x18001468d  mov     rcx, [rcx+10h]
0x180014691  lea     r8, WPP_0955e053d70b3b28b837838791dca877_Traceguids
0x180014698  mov     edx, 11h
0x18001469d  call    WPP_SF_
0x1800146a2  mov     eax, 80004001h
0x1800146a7  add     rsp, 28h
0x1800146ab  retn
```

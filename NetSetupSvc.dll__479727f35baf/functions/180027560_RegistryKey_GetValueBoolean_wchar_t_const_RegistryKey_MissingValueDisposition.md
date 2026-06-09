# RegistryKey::GetValueBoolean(wchar_t const *,RegistryKey::MissingValueDisposition)

- ea: `0x180027560`
- end: `0x1800275de`
- name: `?GetValueBoolean@RegistryKey@@QEBA_NPEB_WW4MissingValueDisposition@1@@Z`
- size: `126`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180009cfc`
- `0x18000b2c0`
- `0x18000b4b4`
- `0x18001eb14`
- `0x180021650`

## callees

- `0x1800032e4`
- `0x1800078f8`
- `0x180008854`
- `0x180027560`
- `0x1800275e4`

## pseudocode

```c
char __fastcall RegistryKey::GetValueBoolean(__int64 a1, __int64 a2)
{
  unsigned int ValueDword; // eax
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF

  ValueDword = RegistryKey::GetValueDword(a1, a2, 0, 1);
  if ( !ValueDword )
    return 0;
  if ( ValueDword != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids, ValueDword);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024883);
    throw (HResultException *)pExceptionObject;
  }
  return 1;
}

```

## disassembly

```asm
0x180027560  sub     rsp, 0F8h
0x180027567  mov     r9d, 1
0x18002756d  xor     r8d, r8d
0x180027570  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180027575  mov     r9d, eax
0x180027578  test    eax, eax
0x18002757a  jz      short loc_1800275D4
0x18002757c  cmp     eax, 1
0x18002757f  jz      short loc_1800275D0
0x180027581  mov     rcx, cs:WPP_GLOBAL_Control
0x180027588  lea     rax, WPP_GLOBAL_Control
0x18002758f  cmp     rcx, rax
0x180027592  jz      short loc_1800275AF
0x180027594  cmp     byte ptr [rcx+19h], 2
0x180027598  jb      short loc_1800275AF
0x18002759a  mov     rcx, [rcx+10h]
0x18002759e  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x1800275a5  mov     edx, 16h
0x1800275aa  call    WPP_SF_d
0x1800275af  mov     edx, 8007000Dh; int
0x1800275b4  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x1800275b9  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800275be  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800275c5  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800275ca  call    _CxxThrowException_0
0x1800275d0  mov     al, 1
0x1800275d2  jmp     short loc_1800275D6
0x1800275d4  xor     al, al
0x1800275d6  add     rsp, 0F8h
0x1800275dd  retn
```

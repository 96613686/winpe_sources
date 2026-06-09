# imp_ApxCircuitInitSetComponentId

- ea: `0x1800162e0`
- end: `0x1800163a4`
- name: `imp_ApxCircuitInitSetComponentId`
- size: `196`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a12c`
- `0x18000a8e8`
- `0x18000a948`
- `0x1800162e0`

## string_xrefs

- `0x18001634c`: `(PVOID)ComponentId`

## pseudocode

```c
__int64 __fastcall imp_ApxCircuitInitSetComponentId(Apx::ApfVerify *this, Apx::ApfVerify *a2, Apx::ApfVerify *a3)
{
  __int64 result; // rax
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r8
  unsigned __int64 v9; // rbx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d0555f171fc53556c80428ad98b2b367_Traceguids);
  }
  result = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( (int)result >= 0 )
  {
    result = Apx::ApfVerify::IsNotNull(a2, L"CircuitInit", v7);
    if ( (int)result >= 0 )
    {
      result = Apx::ApfVerify::IsNotNull(a3, L"(PVOID)ComponentId", v8);
      if ( (int)result >= 0 )
      {
        v9 = ~(unsigned __int64)a2;
        *(_DWORD *)(v9 + 24) |= 2u;
        *(_OWORD *)(v9 + 28) = *(_OWORD *)a3;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_d0555f171fc53556c80428ad98b2b367_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x1800162e0  push    rbx
0x1800162e2  push    rbp
0x1800162e3  push    rsi
0x1800162e4  push    rdi
0x1800162e5  sub     rsp, 28h
0x1800162e9  mov     rdi, r8
0x1800162ec  mov     rbx, rdx
0x1800162ef  mov     rsi, rcx
0x1800162f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800162f9  lea     rbp, WPP_GLOBAL_Control
0x180016300  cmp     rcx, rbp
0x180016303  jz      short loc_180016326
0x180016305  test    byte ptr [rcx+1Ch], 1
0x180016309  jz      short loc_180016326
0x18001630b  cmp     byte ptr [rcx+19h], 5
0x18001630f  jb      short loc_180016326
0x180016311  mov     rcx, [rcx+10h]
0x180016315  lea     r8, WPP_d0555f171fc53556c80428ad98b2b367_Traceguids
0x18001631c  mov     edx, 0Eh
0x180016321  call    WPP_SF_
0x180016326  lea     rdx, aGlobals; "Globals"
0x18001632d  mov     rcx, rsi; this
0x180016330  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x180016335  test    eax, eax
0x180016337  js      short loc_18001636E
0x180016339  lea     rdx, aCircuitinit; "CircuitInit"
0x180016340  mov     rcx, rbx; this
0x180016343  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x180016348  test    eax, eax
0x18001634a  js      short loc_18001636E
0x18001634c  lea     rdx, aPvoidComponent; "(PVOID)ComponentId"
0x180016353  mov     rcx, rdi; this
0x180016356  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001635b  test    eax, eax
0x18001635d  js      short loc_18001636E
0x18001635f  not     rbx
0x180016362  or      dword ptr [rbx+18h], 2
0x180016366  movups  xmm0, xmmword ptr [rdi]
0x180016369  movdqu  xmmword ptr [rbx+1Ch], xmm0
0x18001636e  mov     rcx, cs:WPP_GLOBAL_Control
0x180016375  cmp     rcx, rbp
0x180016378  jz      short loc_18001639B
0x18001637a  test    byte ptr [rcx+1Ch], 1
0x18001637e  jz      short loc_18001639B
0x180016380  cmp     byte ptr [rcx+19h], 5
0x180016384  jb      short loc_18001639B
0x180016386  mov     rcx, [rcx+10h]
0x18001638a  lea     r8, WPP_d0555f171fc53556c80428ad98b2b367_Traceguids
0x180016391  mov     edx, 0Fh
0x180016396  call    WPP_SF_
0x18001639b  add     rsp, 28h
0x18001639f  pop     rdi
0x1800163a0  pop     rsi
0x1800163a1  pop     rbp
0x1800163a2  pop     rbx
0x1800163a3  retn
```

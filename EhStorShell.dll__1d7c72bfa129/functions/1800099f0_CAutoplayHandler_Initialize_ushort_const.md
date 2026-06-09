# CAutoplayHandler::Initialize(ushort const *)

- ea: `0x1800099f0`
- end: `0x180009ab7`
- name: `?Initialize@CAutoplayHandler@@UEAAJPEBG@Z`
- size: `199`
- prototype: `__int64 __fastcall(CAutoplayHandler *this, const unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800066c0`
- `0x18000684c`
- `0x1800099f0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180009a47`
- `KERNEL32!CompareStringW` at `0x180009a47`

## pseudocode

```c
__int64 __fastcall CAutoplayHandler::Initialize(
        CAutoplayHandler *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // r9
  unsigned int v6; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, a4);
  if ( CompareStringW(0, 0, a2, -1, L"Authorize", -1) == 2 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, v5);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids, a2);
    return (unsigned int)-2147467263;
  }
  return v6;
}

```

## disassembly

```asm
0x1800099f0  mov     [rsp+arg_0], rbx
0x1800099f5  push    rdi
0x1800099f6  sub     rsp, 30h
0x1800099fa  mov     rbx, rdx
0x1800099fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a04  lea     rdi, WPP_GLOBAL_Control
0x180009a0b  cmp     rcx, rdi
0x180009a0e  jz      short loc_180009A2B
0x180009a10  test    byte ptr [rcx+1Ch], 20h
0x180009a14  jz      short loc_180009A2B
0x180009a16  mov     rcx, [rcx+10h]
0x180009a1a  lea     r8, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids
0x180009a21  mov     edx, 0Dh
0x180009a26  call    WPP_SF_
0x180009a2b  or      r9d, 0FFFFFFFFh; cchCount1
0x180009a2f  lea     rax, aAuthorize; "Authorize"
0x180009a36  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x180009a3b  mov     r8, rbx; lpString1
0x180009a3e  xor     edx, edx; dwCmpFlags
0x180009a40  mov     [rsp+38h+lpString2], rax; lpString2
0x180009a45  xor     ecx, ecx; Locale
0x180009a47  call    cs:__imp_CompareStringW
0x180009a4d  cmp     eax, 2
0x180009a50  jz      short loc_180009A83
0x180009a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a59  cmp     rcx, rdi
0x180009a5c  jz      short loc_180009A7C
0x180009a5e  test    byte ptr [rcx+1Ch], 2
0x180009a62  jz      short loc_180009A7C
0x180009a64  mov     rcx, [rcx+10h]
0x180009a68  lea     r8, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids
0x180009a6f  mov     edx, 0Eh
0x180009a74  mov     r9, rbx
0x180009a77  call    WPP_SF_S
0x180009a7c  mov     ebx, 80004001h
0x180009a81  jmp     short loc_180009AAA
0x180009a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a8a  xor     ebx, ebx
0x180009a8c  cmp     rcx, rdi
0x180009a8f  jz      short loc_180009AAA
0x180009a91  test    byte ptr [rcx+1Ch], 20h
0x180009a95  jz      short loc_180009AAA
0x180009a97  mov     rcx, [rcx+10h]
0x180009a9b  lea     edx, [rbx+0Fh]
0x180009a9e  lea     r8, WPP_0b4c1107a16c3139badecedb00031f47_Traceguids
0x180009aa5  call    WPP_SF_
0x180009aaa  mov     eax, ebx
0x180009aac  mov     rbx, [rsp+38h+arg_0]
0x180009ab1  add     rsp, 30h
0x180009ab5  pop     rdi
0x180009ab6  retn
```

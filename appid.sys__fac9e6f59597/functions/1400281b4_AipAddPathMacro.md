# AipAddPathMacro

- ea: `0x1400281b4`
- end: `0x1400282f9`
- name: `AipAddPathMacro`
- size: `325`
- prototype: `__int64 __fastcall(const UNICODE_STRING *, const UNICODE_STRING *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x140027ebc`
- `0x140028040`

## callees

- `0x140001f58`
- `0x1400281b4`
- `0x1400328b0`
- `0x140032a50`
- `0x1400365f0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400281d3`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400281d3`

## pseudocode

```c
__int64 __fastcall AipAddPathMacro(const UNICODE_STRING *a1, const UNICODE_STRING *a2, int a3)
{
  const UNICODE_STRING *v4; // rdi
  int v6; // esi
  _QWORD *v7; // rbx
  PWSTR Buffer; // rcx
  __int64 v9; // rax
  _OWORD v11[3]; // [rsp+30h] [rbp-38h] BYREF

  v4 = a2;
  v11[0] = 0;
  if ( RtlEqualUnicodeString(a1, a2, 1u) )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    v7 = (_QWORD *)AiAlloc(0x38u);
    if ( v7 )
    {
      v6 = 0;
      if ( (a3 & 8) != 0 )
      {
        v6 = AipConvertToNtPath(v4, v11);
        if ( v6 < 0 )
        {
          AiFree(v7);
          return (unsigned int)v6;
        }
        Buffer = v4->Buffer;
        if ( *((PWSTR *)&v11[0] + 1) != Buffer )
        {
          if ( (a3 & 2) != 0 )
          {
            AiFree(Buffer);
            v4->Buffer = 0;
          }
          a3 |= 2u;
          v4 = (const UNICODE_STRING *)v11;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_4affb847aa64312eeff433e6518e017d_Traceguids,
          (_DWORD)a1,
          (__int64)v4);
      *((_DWORD *)v7 + 4) = a3;
      *(UNICODE_STRING *)(v7 + 3) = *a1;
      if ( (a3 & 1) != 0 )
        a1->Buffer = 0;
      *(UNICODE_STRING *)(v7 + 5) = *v4;
      if ( (a3 & 2) != 0 )
        v4->Buffer = 0;
      v9 = qword_1400195B8;
      if ( *(__int64 **)(qword_1400195B8 + 8) != &qword_1400195B8 )
        __fastfail(3u);
      *v7 = qword_1400195B8;
      v7[1] = &qword_1400195B8;
      *(_QWORD *)(v9 + 8) = v7;
      qword_1400195B8 = (__int64)v7;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400281b4  push    rbx
0x1400281b6  push    rbp
0x1400281b7  push    rsi
0x1400281b8  push    rdi
0x1400281b9  push    r14
0x1400281bb  sub     rsp, 40h
0x1400281bf  mov     ebp, r8d
0x1400281c2  xorps   xmm0, xmm0
0x1400281c5  mov     r8b, 1; CaseInSensitive
0x1400281c8  mov     rdi, rdx
0x1400281cb  movups  [rsp+68h+var_38], xmm0
0x1400281d0  mov     r14, rcx
0x1400281d3  call    cs:__imp_RtlEqualUnicodeString
0x1400281da  nop     dword ptr [rax+rax+00h]
0x1400281df  test    al, al
0x1400281e1  jz      short loc_1400281ED
0x1400281e3  mov     esi, 0C000000Dh
0x1400281e8  jmp     loc_1400282EB
0x1400281ed  mov     ecx, 38h ; '8'
0x1400281f2  call    AiAlloc
0x1400281f7  mov     rbx, rax
0x1400281fa  test    rax, rax
0x1400281fd  jnz     short loc_140028209
0x1400281ff  mov     esi, 0C0000017h
0x140028204  jmp     loc_1400282EB
0x140028209  xor     esi, esi
0x14002820b  test    bpl, 8
0x14002820f  jz      short loc_140028257
0x140028211  lea     rdx, [rsp+68h+var_38]
0x140028216  mov     rcx, rdi
0x140028219  call    AipConvertToNtPath
0x14002821e  mov     esi, eax
0x140028220  test    eax, eax
0x140028222  jns     short loc_140028231
0x140028224  mov     rcx, rbx
0x140028227  call    AiFree
0x14002822c  jmp     loc_1400282EB
0x140028231  mov     rcx, [rdi+8]
0x140028235  cmp     qword ptr [rsp+68h+var_38+8], rcx
0x14002823a  jz      short loc_140028257
0x14002823c  test    bpl, 2
0x140028240  jz      short loc_14002824F
0x140028242  call    AiFree
0x140028247  mov     qword ptr [rdi+8], 0
0x14002824f  or      ebp, 2
0x140028252  lea     rdi, [rsp+68h+var_38]
0x140028257  mov     rcx, cs:WPP_GLOBAL_Control
0x14002825e  lea     rax, WPP_GLOBAL_Control
0x140028265  cmp     rcx, rax
0x140028268  jz      short loc_14002828E
0x14002826a  mov     eax, [rcx+2Ch]
0x14002826d  test    al, 10h
0x14002826f  jz      short loc_14002828E
0x140028271  mov     rcx, [rcx+18h]
0x140028275  lea     r8, WPP_4affb847aa64312eeff433e6518e017d_Traceguids
0x14002827c  mov     edx, 0Ah
0x140028281  mov     [rsp+68h+var_48], rdi
0x140028286  mov     r9, r14
0x140028289  call    WPP_SF_ZZ
0x14002828e  mov     [rbx+10h], ebp
0x140028291  movups  xmm0, xmmword ptr [r14]
0x140028295  movdqu  xmmword ptr [rbx+18h], xmm0
0x14002829a  test    bpl, 1
0x14002829e  jz      short loc_1400282A8
0x1400282a0  mov     qword ptr [r14+8], 0
0x1400282a8  movups  xmm0, xmmword ptr [rdi]
0x1400282ab  movdqu  xmmword ptr [rbx+28h], xmm0
0x1400282b0  test    bpl, 2
0x1400282b4  jz      short loc_1400282BE
0x1400282b6  mov     qword ptr [rdi+8], 0
0x1400282be  mov     rax, cs:qword_1400195B8
0x1400282c5  lea     rcx, qword_1400195B8
0x1400282cc  cmp     [rax+8], rcx
0x1400282d0  jz      short loc_1400282D9
0x1400282d2  mov     ecx, 3
0x1400282d7  int     29h; Win8: RtlFailFast(ecx)
0x1400282d9  mov     [rbx], rax
0x1400282dc  mov     [rbx+8], rcx
0x1400282e0  mov     [rax+8], rbx
0x1400282e4  mov     cs:qword_1400195B8, rbx
0x1400282eb  mov     eax, esi
0x1400282ed  add     rsp, 40h
0x1400282f1  pop     r14
0x1400282f3  pop     rdi
0x1400282f4  pop     rsi
0x1400282f5  pop     rbp
0x1400282f6  pop     rbx
0x1400282f7  retn
```

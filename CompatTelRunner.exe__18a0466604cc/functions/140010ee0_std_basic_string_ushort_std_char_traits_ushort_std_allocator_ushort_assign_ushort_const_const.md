# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const * const)

- ea: `0x140010ee0`
- end: `0x140010ff8`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z`
- size: `280`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000f190`

## callees

- `0x140001e34`
- `0x14000e18c`
- `0x140010ee0`
- `0x1400a7314`

## string_xrefs

- `0x140010f04`: `DELETE FROM Metadata`
- `0x140010f7a`: `DELETE FROM Metadata`

## pseudocode

```c
__int64 *__fastcall std::wstring::assign(__int64 *a1, __int64 a2)
{
  unsigned __int64 v2; // rbx
  _WORD *v4; // rbx
  __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // rsi
  _WORD *v8; // rax
  _BYTE *v9; // rcx
  __int64 v11; // [rsp+38h] [rbp+10h] BYREF

  v11 = a2;
  v2 = a1[3];
  if ( v2 < 0x14 )
  {
    v5 = 0x7FFFFFFFFFFFFFFELL;
    v6 = v2 >> 1;
    if ( v2 <= 0x7FFFFFFFFFFFFFFELL - (v2 >> 1) )
    {
      v5 = 23;
      if ( v6 + v2 > 0x17 )
        v5 = v6 + v2;
    }
    v11 = v5;
    v7 = std::wstring::_Allocate_for_capacity<0>(v5, &v11);
    a1[3] = v11;
    a1[2] = 20;
    *(_OWORD *)v7 = *(_OWORD *)L"DELETE FROM Metadata";
    *(_OWORD *)(v7 + 16) = *(_OWORD *)L"ROM Metadata";
    *(_QWORD *)(v7 + 32) = *(_QWORD *)L"data";
    *(_WORD *)(v7 + 40) = 0;
    if ( v2 > 7 )
    {
      v8 = (_WORD *)*a1;
      if ( 2 * v2 + 2 < 0x1000 )
      {
        v9 = (_BYTE *)*a1;
      }
      else
      {
        v9 = (_BYTE *)*((_QWORD *)v8 - 1);
        if ( (unsigned __int64)((char *)v8 - v9 - 8) > 0x1F )
          __fastfail(5u);
      }
      operator delete(v9);
    }
    *a1 = v7;
  }
  else
  {
    v4 = (_WORD *)*a1;
    a1[2] = 20;
    memmove_0(v4, L"DELETE FROM Metadata", 0x28u);
    v4[20] = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x140010ee0  mov     [rsp+arg_0], rbx
0x140010ee5  mov     [rsp+arg_10], rsi
0x140010eea  mov     [rsp+arg_8], rdx
0x140010eef  push    rdi
0x140010ef0  sub     rsp, 20h
0x140010ef4  mov     rbx, [rcx+18h]
0x140010ef8  mov     rdi, rcx
0x140010efb  cmp     rbx, 14h
0x140010eff  jb      short loc_140010F2C
0x140010f01  mov     rbx, [rcx]
0x140010f04  lea     rdx, aDeleteFromMeta; "DELETE FROM Metadata"
0x140010f0b  mov     qword ptr [rcx+10h], 14h
0x140010f13  mov     r8d, 28h ; '('; Size
0x140010f19  mov     rcx, rbx; void *
0x140010f1c  call    memmove_0
0x140010f21  xor     eax, eax
0x140010f23  mov     [rbx+28h], ax
0x140010f27  jmp     loc_140010FE5
0x140010f2c  mov     rdx, rbx
0x140010f2f  mov     rcx, 7FFFFFFFFFFFFFFEh
0x140010f39  shr     rdx, 1
0x140010f3c  mov     rax, rcx
0x140010f3f  sub     rax, rdx
0x140010f42  cmp     rbx, rax
0x140010f45  ja      short loc_140010F57
0x140010f47  lea     rax, [rdx+rbx]
0x140010f4b  mov     ecx, 17h
0x140010f50  cmp     rax, rcx
0x140010f53  cmova   rcx, rax
0x140010f57  lea     rdx, [rsp+28h+arg_8]
0x140010f5c  mov     [rsp+28h+arg_8], rcx
0x140010f61  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CAPEAGAEAV?$allocator@G@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<ushort> &,unsigned __int64 &)
0x140010f66  mov     rcx, [rsp+28h+arg_8]
0x140010f6b  mov     rsi, rax
0x140010f6e  mov     [rdi+18h], rcx
0x140010f72  mov     qword ptr [rdi+10h], 14h
0x140010f7a  movups  xmm0, xmmword ptr cs:aDeleteFromMeta; "DELETE FROM Metadata"
0x140010f81  movups  xmmword ptr [rax], xmm0
0x140010f84  movups  xmm1, xmmword ptr cs:aDeleteFromMeta+10h; "ROM Metadata"
0x140010f8b  movups  xmmword ptr [rax+10h], xmm1
0x140010f8f  movsd   xmm0, qword ptr cs:aDeleteFromMeta+20h; "data"
0x140010f97  movsd   qword ptr [rax+20h], xmm0
0x140010f9c  xor     eax, eax
0x140010f9e  mov     [rsi+28h], ax
0x140010fa2  cmp     rbx, 7
0x140010fa6  jbe     short loc_140010FE2
0x140010fa8  mov     rax, [rdi]
0x140010fab  lea     rdx, ds:2[rbx*2]; unsigned __int64
0x140010fb3  cmp     rdx, 1000h
0x140010fba  jb      short loc_140010FDA
0x140010fbc  mov     rcx, [rax-8]
0x140010fc0  sub     rax, rcx
0x140010fc3  sub     rax, 8
0x140010fc7  cmp     rax, 1Fh
0x140010fcb  ja      short loc_140010FD3
0x140010fcd  add     rdx, 27h ; '''
0x140010fd1  jmp     short loc_140010FDD
0x140010fd3  mov     ecx, 5
0x140010fd8  int     29h; Win8: RtlFailFast(ecx)
0x140010fda  mov     rcx, rax; void *
0x140010fdd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140010fe2  mov     [rdi], rsi
0x140010fe5  mov     rbx, [rsp+28h+arg_0]
0x140010fea  mov     rax, rdi
0x140010fed  mov     rsi, [rsp+28h+arg_10]
0x140010ff2  add     rsp, 20h
0x140010ff6  pop     rdi
0x140010ff7  retn
```

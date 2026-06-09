# CAACDec::GetSupportedChannelConfig(void)

- ea: `0x18000467c`
- end: `0x180004771`
- name: `?GetSupportedChannelConfig@CAACDec@@AEAAHXZ`
- size: `245`
- prototype: `__int64 __fastcall(CAACDec *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180041e50`

## callees

- `0x180003af0`
- `0x18000467c`
- `0x18005b714`

## string_xrefs

- `0x1800046c9`: `CAACDec::GetSupportedChannelConfig`
- `0x1800046bc`: `CAACDec::GetSupportedChannelConfig() unsupported channel config: %d`

## pseudocode

```c
__int64 __fastcall CAACDec::GetSupportedChannelConfig(CAACDec *this)
{
  CAACDec *v1; // r9
  __int64 v2; // rcx
  unsigned __int8 v3; // r11
  int v4; // ebx
  bool v5; // cc
  int v7; // r8d
  _DWORD *v8; // rax
  _DWORD *v9; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rax
  __int64 v12; // r8

  v1 = this;
  v2 = *((_QWORD *)this + 30746);
  v3 = 2;
  v4 = *(_DWORD *)(v2 + 60);
  v5 = v4 <= 0;
  if ( !v4 )
  {
    v7 = *(_DWORD *)(v2 + 12);
    if ( v7 == 2 )
    {
      v8 = *(_DWORD **)(v2 + 16);
      if ( *v8 == 1 && v8[1] == 1 && *(_DWORD *)(v2 + 32) == 2 )
      {
        v9 = *(_DWORD **)(v2 + 40);
        if ( !*v9 && !v9[1] )
          return 10;
      }
    }
    else if ( v7 == 3 )
    {
      v10 = *(_DWORD **)(v2 + 16);
      if ( *v10 == 1 && v10[1] == 1 && v10[2] == 3 && *(_DWORD *)(v2 + 32) == 2 )
      {
        v11 = *(_DWORD **)(v2 + 40);
        if ( *v11 == 1 && !v11[1] )
          return 8;
      }
    }
    if ( Is2_2Config((const struct CStreamInfo *)v2) )
      return 9;
    v4 = *((_DWORD *)qword_1800B7408 + v12);
    v5 = v4 <= 0;
  }
  if ( v5 || v4 == 7 || v4 >= 11 )
    TraceLoggingHelperBase::TraceVA(
      (CAACDec *)((char *)v1 + 246488),
      v3,
      "CAACDec::GetSupportedChannelConfig",
      0x957u,
      "CAACDec::GetSupportedChannelConfig() unsupported channel config: %d",
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000467c  push    rbx
0x18000467e  sub     rsp, 30h
0x180004682  mov     r9, rcx
0x180004685  xor     r10d, r10d
0x180004688  mov     rcx, [rcx+3C0D0h]; struct CStreamInfo *
0x18000468f  mov     r11d, 2
0x180004695  mov     ebx, [rcx+3Ch]
0x180004698  test    ebx, ebx
0x18000469a  jz      short loc_1800046DF
0x18000469c  jle     short loc_1800046B1
0x18000469e  cmp     ebx, 7
0x1800046a1  jz      short loc_1800046B1
0x1800046a3  cmp     ebx, 0Bh
0x1800046a6  jge     short loc_1800046B1
0x1800046a8  mov     eax, ebx
0x1800046aa  add     rsp, 30h
0x1800046ae  pop     rbx
0x1800046af  retn
0x1800046b1  lea     rcx, [r9+3C2D8h]; this
0x1800046b8  mov     [rsp+38h+var_10], ebx
0x1800046bc  lea     rax, aCaacdecGetsupp; "CAACDec::GetSupportedChannelConfig() un"...
0x1800046c3  mov     r9d, 957h; unsigned int
0x1800046c9  lea     r8, aCaacdecGetsupp_0; "CAACDec::GetSupportedChannelConfig"
0x1800046d0  mov     [rsp+38h+Format], rax; Format
0x1800046d5  mov     edx, r11d; unsigned __int8
0x1800046d8  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800046dd  jmp     short loc_1800046A8
0x1800046df  movsxd  r8, dword ptr [rcx+0Ch]
0x1800046e3  cmp     r8d, r11d
0x1800046e6  jnz     short loc_180004713
0x1800046e8  mov     rax, [rcx+10h]
0x1800046ec  cmp     dword ptr [rax], 1
0x1800046ef  jnz     short loc_18000474C
0x1800046f1  cmp     dword ptr [rax+4], 1
0x1800046f5  jnz     short loc_18000474C
0x1800046f7  cmp     [rcx+20h], r11d
0x1800046fb  jnz     short loc_18000474C
0x1800046fd  mov     rax, [rcx+28h]
0x180004701  cmp     [rax], r10d
0x180004704  jnz     short loc_18000474C
0x180004706  cmp     [rax+4], r10d
0x18000470a  jnz     short loc_18000474C
0x18000470c  mov     ebx, 0Ah
0x180004711  jmp     short loc_1800046A8
0x180004713  cmp     r8d, 3
0x180004717  jnz     short loc_18000474C
0x180004719  mov     rax, [rcx+10h]
0x18000471d  cmp     dword ptr [rax], 1
0x180004720  jnz     short loc_18000474C
0x180004722  cmp     dword ptr [rax+4], 1
0x180004726  jnz     short loc_18000474C
0x180004728  cmp     [rax+8], r8d
0x18000472c  jnz     short loc_18000474C
0x18000472e  cmp     [rcx+20h], r11d
0x180004732  jnz     short loc_18000474C
0x180004734  mov     rax, [rcx+28h]
0x180004738  cmp     dword ptr [rax], 1
0x18000473b  jnz     short loc_18000474C
0x18000473d  cmp     [rax+4], r10d
0x180004741  jnz     short loc_18000474C
0x180004743  lea     ebx, [r8+5]
0x180004747  jmp     loc_1800046A8
0x18000474c  call    ?Is2_2Config@@YA_NPEBUCStreamInfo@@@Z; Is2_2Config(CStreamInfo const *)
0x180004751  test    al, al
0x180004753  jz      short loc_18000475F
0x180004755  mov     ebx, 9
0x18000475a  jmp     loc_1800046A8
0x18000475f  lea     rbx, qword_1800B7408
0x180004766  mov     ebx, [rbx+r8*4]
0x18000476a  test    ebx, ebx
0x18000476c  jmp     loc_18000469C
```

# std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>>::push_back(APPID_PLUGIN_ const &)

- ea: `0x140006e60`
- end: `0x140006f0e`
- name: `?push_back@?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@QEAAXAEBUAPPID_PLUGIN_@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140003330`

## callees

- `0x140006c10`
- `0x140006e60`

## pseudocode

```c
__int64 __fastcall std::vector<APPID_PLUGIN_>::push_back(__int64 *a1, unsigned __int64 a2)
{
  bool v4; // al
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 result; // rax

  v4 = a2 < a1[1] && *a1 <= a2;
  v5 = a1[2];
  if ( v4 )
  {
    v6 = (__int64)(a2 - *a1) / 36;
    if ( a1[1] == v5 )
      std::vector<APPID_PLUGIN_>::_Reserve(a1);
    v7 = *a1;
    v8 = a1[1];
    *(_OWORD *)v8 = *(_OWORD *)(*a1 + 36 * v6);
    *(_OWORD *)(v8 + 16) = *(_OWORD *)(v7 + 36 * v6 + 16);
    result = *(unsigned int *)(v7 + 36 * v6 + 32);
  }
  else
  {
    if ( a1[1] == v5 )
      std::vector<APPID_PLUGIN_>::_Reserve(a1);
    v8 = a1[1];
    *(_OWORD *)v8 = *(_OWORD *)a2;
    *(_OWORD *)(v8 + 16) = *(_OWORD *)(a2 + 16);
    result = *(unsigned int *)(a2 + 32);
  }
  *(_DWORD *)(v8 + 32) = result;
  a1[1] += 36;
  return result;
}

```

## disassembly

```asm
0x140006e60  mov     [rsp+arg_0], rbx
0x140006e65  push    rdi
0x140006e66  sub     rsp, 20h
0x140006e6a  mov     rdi, rdx
0x140006e6d  mov     rbx, rcx
0x140006e70  cmp     rdx, [rcx+8]
0x140006e74  jnb     short loc_140006E7F
0x140006e76  cmp     [rcx], rdx
0x140006e79  ja      short loc_140006E7F
0x140006e7b  mov     al, 1
0x140006e7d  jmp     short loc_140006E81
0x140006e7f  xor     al, al
0x140006e81  mov     rcx, [rcx+10h]
0x140006e85  test    al, al
0x140006e87  jz      short loc_140006ED8
0x140006e89  sub     rdi, [rbx]
0x140006e8c  mov     rax, 0E38E38E38E38E39h
0x140006e96  imul    rdi
0x140006e99  mov     rdi, rdx
0x140006e9c  sar     rdi, 1
0x140006e9f  mov     rax, rdi
0x140006ea2  shr     rax, 3Fh
0x140006ea6  add     rdi, rax
0x140006ea9  cmp     [rbx+8], rcx
0x140006ead  jnz     short loc_140006EB7
0x140006eaf  mov     rcx, rbx
0x140006eb2  call    ?_Reserve@?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@IEAAX_K@Z; std::vector<APPID_PLUGIN_>::_Reserve(unsigned __int64)
0x140006eb7  mov     rax, [rbx]
0x140006eba  lea     rdx, [rdi+rdi*8]
0x140006ebe  mov     rcx, [rbx+8]
0x140006ec2  movups  xmm0, xmmword ptr [rax+rdx*4]
0x140006ec6  movups  xmmword ptr [rcx], xmm0
0x140006ec9  movups  xmm1, xmmword ptr [rax+rdx*4+10h]
0x140006ece  movups  xmmword ptr [rcx+10h], xmm1
0x140006ed2  mov     eax, [rax+rdx*4+20h]
0x140006ed6  jmp     short loc_140006EFB
0x140006ed8  cmp     [rbx+8], rcx
0x140006edc  jnz     short loc_140006EE6
0x140006ede  mov     rcx, rbx
0x140006ee1  call    ?_Reserve@?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@IEAAX_K@Z; std::vector<APPID_PLUGIN_>::_Reserve(unsigned __int64)
0x140006ee6  mov     rcx, [rbx+8]
0x140006eea  movups  xmm0, xmmword ptr [rdi]
0x140006eed  movups  xmmword ptr [rcx], xmm0
0x140006ef0  movups  xmm1, xmmword ptr [rdi+10h]
0x140006ef4  movups  xmmword ptr [rcx+10h], xmm1
0x140006ef8  mov     eax, [rdi+20h]
0x140006efb  mov     [rcx+20h], eax
0x140006efe  add     qword ptr [rbx+8], 24h ; '$'
0x140006f03  mov     rbx, [rsp+28h+arg_0]
0x140006f08  add     rsp, 20h
0x140006f0c  pop     rdi
0x140006f0d  retn
```

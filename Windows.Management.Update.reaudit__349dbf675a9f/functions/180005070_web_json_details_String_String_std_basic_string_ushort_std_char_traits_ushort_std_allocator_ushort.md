# web::json::details::_String::_String(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180005070`
- end: `0x18000517b`
- name: `??0_String@details@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `267`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180005330`
- `0x180006fb0`

## callees

- `0x180002c74`
- `0x180005070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005174`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005174`

## pseudocode

```c
__int64 __fastcall web::json::details::_String::_String(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rax
  __int64 v5; // rcx
  _QWORD *v6; // r8
  __int16 v7; // cx
  char v8; // al
  unsigned __int64 v9; // rdx
  char *v10; // rcx
  unsigned __int64 v11; // rdx
  char *v12; // r8
  unsigned __int64 v13; // rdx
  char *v14; // rcx
  __int64 result; // rax

  *(_QWORD *)a1 = &web::json::details::_String::`vftable';
  v3 = (_QWORD *)(a1 + 8);
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 8) = *(_OWORD *)a2;
  *(_OWORD *)(a1 + 24) = *(_OWORD *)(a2 + 16);
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  v5 = *(_QWORD *)(a1 + 24);
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  v6 = (_QWORD *)((char *)v3 + 2 * v5);
  if ( v3 == v6 )
  {
LABEL_8:
    v8 = 0;
  }
  else
  {
    while ( 1 )
    {
      v7 = *(_WORD *)v3;
      if ( *(_WORD *)v3 <= 0x1Fu || v7 == 34 || v7 == 92 )
        break;
      v3 = (_QWORD *)((char *)v3 + 2);
      if ( v3 == v6 )
        goto LABEL_8;
    }
    v8 = 1;
  }
  *(_BYTE *)(a1 + 40) = v8;
  v9 = *(_QWORD *)(a2 + 24);
  if ( v9 > 7 )
  {
    v10 = *(char **)a2;
    v11 = 2 * v9 + 2;
    if ( v11 >= 0x1000 )
    {
      v12 = (char *)*((_QWORD *)v10 - 1);
      v13 = v11 + 39;
      v14 = (char *)(v10 - v12);
      if ( (unsigned __int64)(v14 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v14, v13);
        JUMPOUT(0x18000517ALL);
      }
      v10 = v12;
    }
    operator delete(v10);
  }
  *(_QWORD *)(a2 + 16) = 0;
  result = a1;
  *(_WORD *)a2 = 0;
  *(_QWORD *)(a2 + 24) = 7;
  return result;
}

```

## disassembly

```asm
0x180005070  mov     [rsp+arg_10], rbx
0x180005075  mov     [rsp+arg_18], rsi
0x18000507a  push    rdi
0x18000507b  sub     rsp, 30h
0x18000507f  xor     esi, esi
0x180005081  mov     [rsp+38h+var_18], rcx
0x180005086  lea     rax, ??_7_String@details@json@web@@6B@; const web::json::details::_String::`vftable'
0x18000508d  mov     [rsp+38h+var_18], rdx
0x180005092  mov     [rcx], rax
0x180005095  mov     rdi, rcx
0x180005098  lea     rax, [rcx+8]
0x18000509c  xorps   xmm0, xmm0
0x18000509f  movups  xmmword ptr [rax], xmm0
0x1800050a2  mov     [rax+10h], rsi
0x1800050a6  lea     rcx, [rax+10h]
0x1800050aa  mov     [rax+18h], rsi
0x1800050ae  mov     rbx, rdx
0x1800050b1  movups  xmm0, xmmword ptr [rdx]
0x1800050b4  movups  xmmword ptr [rax], xmm0
0x1800050b7  movups  xmm1, xmmword ptr [rdx+10h]
0x1800050bb  movups  xmmword ptr [rax+10h], xmm1
0x1800050bf  mov     [rdx+10h], rsi
0x1800050c3  mov     qword ptr [rdx+18h], 7
0x1800050cb  mov     [rdx], si
0x1800050ce  cmp     qword ptr [rax+18h], 7
0x1800050d3  mov     rcx, [rcx]
0x1800050d6  jbe     short loc_1800050E4
0x1800050d8  mov     rdx, [rax]
0x1800050db  mov     rax, rdx
0x1800050de  lea     r8, [rdx+rcx*2]
0x1800050e2  jmp     short loc_1800050E8
0x1800050e4  lea     r8, [rax+rcx*2]
0x1800050e8  cmp     rax, r8
0x1800050eb  jz      short loc_18000510E
0x1800050ed  nop     dword ptr [rax]
0x1800050f0  movzx   ecx, word ptr [rax]
0x1800050f3  cmp     cx, 1Fh
0x1800050f7  jbe     short loc_180005170
0x1800050f9  cmp     cx, 22h ; '"'
0x1800050fd  jz      short loc_180005170
0x1800050ff  cmp     cx, 5Ch ; '\'
0x180005103  jz      short loc_180005170
0x180005105  add     rax, 2
0x180005109  cmp     rax, r8
0x18000510c  jnz     short loc_1800050F0
0x18000510e  xor     al, al
0x180005110  mov     [rdi+28h], al
0x180005113  mov     rdx, [rbx+18h]
0x180005117  cmp     rdx, 7
0x18000511b  jbe     short loc_18000514E
0x18000511d  mov     rcx, [rbx]
0x180005120  lea     rdx, ds:2[rdx*2]
0x180005128  cmp     rdx, 1000h
0x18000512f  jb      short loc_180005149
0x180005131  mov     r8, [rcx-8]
0x180005135  add     rdx, 27h ; '''; unsigned __int64
0x180005139  sub     rcx, r8
0x18000513c  lea     rax, [rcx-8]
0x180005140  cmp     rax, 1Fh
0x180005144  ja      short loc_180005174
0x180005146  mov     rcx, r8; void *
0x180005149  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000514e  mov     [rbx+10h], rsi
0x180005152  mov     rax, rdi
0x180005155  mov     [rbx], si
0x180005158  mov     rsi, [rsp+38h+arg_18]
0x18000515d  mov     qword ptr [rbx+18h], 7
0x180005165  mov     rbx, [rsp+38h+arg_10]
0x18000516a  add     rsp, 30h
0x18000516e  pop     rdi
0x18000516f  retn
0x180005170  mov     al, 1
0x180005172  jmp     short loc_180005110
0x180005174  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
```

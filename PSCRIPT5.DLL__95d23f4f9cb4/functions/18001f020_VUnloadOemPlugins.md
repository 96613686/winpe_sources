# VUnloadOemPlugins

- ea: `0x18001f020`
- end: `0x18001f1fd`
- name: `VUnloadOemPlugins`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800057c4`

## callees

- `0x18001f020`
- `0x180030480`
- `0x180030bcc`
- `0x18005d010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001f1c5`
- `KERNEL32!LocalFree` at `0x18001f1c5`

## pseudocode

```c
_DWORD *__fastcall VUnloadOemPlugins(_QWORD *a1, DWORD a2)
{
  _DWORD *result; // rax
  int v4; // esi
  char *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rcx
  void (__fastcall *v8)(_QWORD *); // rax
  __int64 v9; // rax
  int v10; // esi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  void (*v14)(void); // rax
  void *v15; // rcx
  _DWORD *v16; // rcx

  result = (_DWORD *)a1[433];
  if ( result )
  {
    v4 = result[2];
    v5 = (char *)(result + 6);
    while ( v4 )
    {
      v6 = *((_QWORD *)v5 + 4);
      --v4;
      if ( v6 )
      {
        a1[4] = v6;
        a1[1] = *((_QWORD *)v5 + 5);
        a1[6] = *((_QWORD *)v5 + 7);
        if ( (v5[48] & 2) != 0 )
        {
          v7 = *((_QWORD *)v5 + 9);
          if ( v7 )
          {
            if ( *((_QWORD *)v5 + 10) == *(_QWORD *)&IID_IPrintOemPS.Data1
              && *((_QWORD *)v5 + 11) == *(_QWORD *)IID_IPrintOemPS.Data4
              || *((_QWORD *)v5 + 10) == *(_QWORD *)&IID_IPrintOemPS2.Data1
              && *((_QWORD *)v5 + 11) == *(_QWORD *)IID_IPrintOemPS2.Data4 )
            {
              (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 64LL))(v7, a1);
            }
          }
          else
          {
            if ( (v5[100] & 0x20) != 0 )
              v8 = (void (__fastcall *)(_QWORD *))*((_QWORD *)v5 + 18);
            else
              v8 = (void (__fastcall *)(_QWORD *))PGetOemEntrypointAddress(v5, 5);
            if ( v8 )
              v8(a1);
          }
        }
      }
      v5 += 176;
    }
    v9 = a1[433];
    v10 = *(_DWORD *)(v9 + 8);
    v11 = v9 + 24;
    while ( v10 )
    {
      v12 = *(_QWORD *)(v11 + 32);
      --v10;
      if ( v12 )
      {
        a1[4] = v12;
        a1[1] = *(_QWORD *)(v11 + 40);
        a1[6] = *(_QWORD *)(v11 + 56);
        if ( (*(_BYTE *)(v11 + 48) & 1) != 0 )
        {
          v13 = *(_QWORD *)(v11 + 72);
          if ( v13 )
          {
            if ( *(_QWORD *)(v11 + 80) == *(_QWORD *)&IID_IPrintOemPS.Data1
              && *(_QWORD *)(v11 + 88) == *(_QWORD *)IID_IPrintOemPS.Data4
              || *(_QWORD *)(v11 + 80) == *(_QWORD *)&IID_IPrintOemPS2.Data1
              && *(_QWORD *)(v11 + 88) == *(_QWORD *)IID_IPrintOemPS2.Data4 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 48LL))(v13);
            }
          }
          else
          {
            if ( (*(_BYTE *)(v11 + 100) & 8) != 0 )
              v14 = *(void (**)(void))(v11 + 128);
            else
              v14 = (void (*)(void))PGetOemEntrypointAddress(v11, 3);
            if ( v14 )
              v14();
          }
        }
      }
      v11 += 176;
    }
    v15 = (void *)a1[434];
    if ( v15 )
      LocalFree(v15);
    v16 = (_DWORD *)a1[433];
    a1[434] = 0;
    result = VFreeOemPluginInfoInternal(v16, a2);
    a1[433] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001f020  mov     [rsp+arg_0], rbx
0x18001f025  mov     [rsp+arg_8], rsi
0x18001f02a  push    rdi
0x18001f02b  sub     rsp, 20h
0x18001f02f  mov     rax, [rcx+0D88h]
0x18001f036  mov     rdi, rcx
0x18001f039  test    rax, rax
0x18001f03c  jz      loc_18001F1ED
0x18001f042  mov     esi, [rax+8]
0x18001f045  lea     rbx, [rax+18h]
0x18001f049  jmp     loc_18001F0F5
0x18001f04e  mov     rax, [rbx+20h]
0x18001f052  dec     esi
0x18001f054  test    rax, rax
0x18001f057  jz      loc_18001F0EE
0x18001f05d  mov     [rdi+20h], rax
0x18001f061  mov     rax, [rbx+28h]
0x18001f065  mov     [rdi+8], rax
0x18001f069  mov     rax, [rbx+38h]
0x18001f06d  mov     [rdi+30h], rax
0x18001f071  test    byte ptr [rbx+30h], 2
0x18001f075  jz      short loc_18001F0EE
0x18001f077  mov     rcx, [rbx+48h]
0x18001f07b  test    rcx, rcx
0x18001f07e  jz      short loc_18001F0C5
0x18001f080  mov     rax, [rbx+50h]
0x18001f084  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x18001f08b  jnz     short loc_18001F09A
0x18001f08d  mov     rax, [rbx+58h]
0x18001f091  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18001f098  jz      short loc_18001F0B4
0x18001f09a  mov     rax, [rbx+50h]
0x18001f09e  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001f0a5  jnz     short loc_18001F0EE
0x18001f0a7  mov     rax, [rbx+58h]
0x18001f0ab  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001f0b2  jnz     short loc_18001F0EE
0x18001f0b4  mov     rax, [rcx]
0x18001f0b7  mov     rdx, rdi
0x18001f0ba  mov     rax, [rax+40h]
0x18001f0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0c3  jmp     short loc_18001F0EE
0x18001f0c5  test    byte ptr [rbx+64h], 20h
0x18001f0c9  jz      short loc_18001F0D4
0x18001f0cb  mov     rax, [rbx+90h]
0x18001f0d2  jmp     short loc_18001F0E1
0x18001f0d4  mov     edx, 5
0x18001f0d9  mov     rcx, rbx
0x18001f0dc  call    PGetOemEntrypointAddress
0x18001f0e1  test    rax, rax
0x18001f0e4  jz      short loc_18001F0EE
0x18001f0e6  mov     rcx, rdi
0x18001f0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ee  add     rbx, 0B0h
0x18001f0f5  test    esi, esi
0x18001f0f7  jnz     loc_18001F04E
0x18001f0fd  mov     rax, [rdi+0D88h]
0x18001f104  mov     esi, [rax+8]
0x18001f107  lea     rbx, [rax+18h]
0x18001f10b  jmp     loc_18001F1B1
0x18001f110  mov     rax, [rbx+20h]
0x18001f114  dec     esi
0x18001f116  test    rax, rax
0x18001f119  jz      loc_18001F1AA
0x18001f11f  mov     [rdi+20h], rax
0x18001f123  mov     rax, [rbx+28h]
0x18001f127  mov     [rdi+8], rax
0x18001f12b  mov     rax, [rbx+38h]
0x18001f12f  mov     [rdi+30h], rax
0x18001f133  test    byte ptr [rbx+30h], 1
0x18001f137  jz      short loc_18001F1AA
0x18001f139  mov     rcx, [rbx+48h]
0x18001f13d  test    rcx, rcx
0x18001f140  jz      short loc_18001F184
0x18001f142  mov     rax, [rbx+50h]
0x18001f146  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x18001f14d  jnz     short loc_18001F15C
0x18001f14f  mov     rax, [rbx+58h]
0x18001f153  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18001f15a  jz      short loc_18001F176
0x18001f15c  mov     rax, [rbx+50h]
0x18001f160  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001f167  jnz     short loc_18001F1AA
0x18001f169  mov     rax, [rbx+58h]
0x18001f16d  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001f174  jnz     short loc_18001F1AA
0x18001f176  mov     rax, [rcx]
0x18001f179  mov     rax, [rax+30h]
0x18001f17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f182  jmp     short loc_18001F1AA
0x18001f184  test    byte ptr [rbx+64h], 8
0x18001f188  jz      short loc_18001F193
0x18001f18a  mov     rax, [rbx+80h]
0x18001f191  jmp     short loc_18001F1A0
0x18001f193  mov     edx, 3
0x18001f198  mov     rcx, rbx
0x18001f19b  call    PGetOemEntrypointAddress
0x18001f1a0  test    rax, rax
0x18001f1a3  jz      short loc_18001F1AA
0x18001f1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1aa  add     rbx, 0B0h
0x18001f1b1  test    esi, esi
0x18001f1b3  jnz     loc_18001F110
0x18001f1b9  mov     rcx, [rdi+0D90h]; hMem
0x18001f1c0  test    rcx, rcx
0x18001f1c3  jz      short loc_18001F1CB
0x18001f1c5  call    cs:__imp_LocalFree
0x18001f1cb  mov     rcx, [rdi+0D88h]
0x18001f1d2  mov     qword ptr [rdi+0D90h], 0
0x18001f1dd  call    VFreeOemPluginInfoInternal
0x18001f1e2  mov     qword ptr [rdi+0D88h], 0
0x18001f1ed  mov     rbx, [rsp+28h+arg_0]
0x18001f1f2  mov     rsi, [rsp+28h+arg_8]
0x18001f1f7  add     rsp, 20h
0x18001f1fb  pop     rdi
0x18001f1fc  retn
```

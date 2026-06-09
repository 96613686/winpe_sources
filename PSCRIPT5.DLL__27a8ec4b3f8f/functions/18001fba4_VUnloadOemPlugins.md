# VUnloadOemPlugins

- ea: `0x18001fba4`
- end: `0x18001fd88`
- name: `VUnloadOemPlugins`
- size: `484`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005858`

## callees

- `0x18001fba4`
- `0x180031a74`
- `0x1800321e4`
- `0x18005f010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18001fd49`
- `KERNEL32!LocalFree` at `0x18001fd49`

## pseudocode

```c
_DWORD *__fastcall VUnloadOemPlugins(_QWORD *a1, DWORD a2)
{
  _DWORD *result; // rax
  int v4; // esi
  __int64 v5; // rbx
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
    v5 = (__int64)(result + 6);
    while ( v4 )
    {
      v6 = *(_QWORD *)(v5 + 32);
      --v4;
      if ( v6 )
      {
        a1[4] = v6;
        a1[1] = *(_QWORD *)(v5 + 40);
        a1[6] = *(_QWORD *)(v5 + 56);
        if ( (*(_BYTE *)(v5 + 48) & 2) != 0 )
        {
          v7 = *(_QWORD *)(v5 + 72);
          if ( v7 )
          {
            if ( *(_QWORD *)(v5 + 80) == *(_QWORD *)&IID_IPrintOemPS.Data1
              && *(_QWORD *)(v5 + 88) == *(_QWORD *)IID_IPrintOemPS.Data4
              || *(_QWORD *)(v5 + 80) == *(_QWORD *)&IID_IPrintOemPS2.Data1
              && *(_QWORD *)(v5 + 88) == *(_QWORD *)IID_IPrintOemPS2.Data4 )
            {
              (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v7 + 64LL))(v7, a1);
            }
          }
          else
          {
            if ( (*(_BYTE *)(v5 + 100) & 0x20) != 0 )
              v8 = *(void (__fastcall **)(_QWORD *))(v5 + 144);
            else
              v8 = (void (__fastcall *)(_QWORD *))PGetOemEntrypointAddress(v5, 5u);
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
              v14 = (void (*)(void))PGetOemEntrypointAddress(v11, 3u);
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
0x18001fba4  mov     [rsp+arg_0], rbx
0x18001fba9  mov     [rsp+arg_8], rsi
0x18001fbae  push    rdi
0x18001fbaf  sub     rsp, 20h
0x18001fbb3  mov     rax, [rcx+0D88h]
0x18001fbba  mov     rdi, rcx
0x18001fbbd  test    rax, rax
0x18001fbc0  jz      loc_18001FD77
0x18001fbc6  mov     esi, [rax+8]
0x18001fbc9  lea     rbx, [rax+18h]
0x18001fbcd  jmp     loc_18001FC79
0x18001fbd2  mov     rax, [rbx+20h]
0x18001fbd6  dec     esi
0x18001fbd8  test    rax, rax
0x18001fbdb  jz      loc_18001FC72
0x18001fbe1  mov     [rdi+20h], rax
0x18001fbe5  mov     rax, [rbx+28h]
0x18001fbe9  mov     [rdi+8], rax
0x18001fbed  mov     rax, [rbx+38h]
0x18001fbf1  mov     [rdi+30h], rax
0x18001fbf5  test    byte ptr [rbx+30h], 2
0x18001fbf9  jz      short loc_18001FC72
0x18001fbfb  mov     rcx, [rbx+48h]
0x18001fbff  test    rcx, rcx
0x18001fc02  jz      short loc_18001FC49
0x18001fc04  mov     rax, [rbx+50h]
0x18001fc08  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x18001fc0f  jnz     short loc_18001FC1E
0x18001fc11  mov     rax, [rbx+58h]
0x18001fc15  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18001fc1c  jz      short loc_18001FC38
0x18001fc1e  mov     rax, [rbx+50h]
0x18001fc22  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001fc29  jnz     short loc_18001FC72
0x18001fc2b  mov     rax, [rbx+58h]
0x18001fc2f  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001fc36  jnz     short loc_18001FC72
0x18001fc38  mov     rax, [rcx]
0x18001fc3b  mov     rdx, rdi
0x18001fc3e  mov     rax, [rax+40h]
0x18001fc42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc47  jmp     short loc_18001FC72
0x18001fc49  test    byte ptr [rbx+64h], 20h
0x18001fc4d  jz      short loc_18001FC58
0x18001fc4f  mov     rax, [rbx+90h]
0x18001fc56  jmp     short loc_18001FC65
0x18001fc58  mov     edx, 5
0x18001fc5d  mov     rcx, rbx
0x18001fc60  call    PGetOemEntrypointAddress
0x18001fc65  test    rax, rax
0x18001fc68  jz      short loc_18001FC72
0x18001fc6a  mov     rcx, rdi
0x18001fc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc72  add     rbx, 0B0h
0x18001fc79  test    esi, esi
0x18001fc7b  jnz     loc_18001FBD2
0x18001fc81  mov     rax, [rdi+0D88h]
0x18001fc88  mov     esi, [rax+8]
0x18001fc8b  lea     rbx, [rax+18h]
0x18001fc8f  jmp     loc_18001FD35
0x18001fc94  mov     rax, [rbx+20h]
0x18001fc98  dec     esi
0x18001fc9a  test    rax, rax
0x18001fc9d  jz      loc_18001FD2E
0x18001fca3  mov     [rdi+20h], rax
0x18001fca7  mov     rax, [rbx+28h]
0x18001fcab  mov     [rdi+8], rax
0x18001fcaf  mov     rax, [rbx+38h]
0x18001fcb3  mov     [rdi+30h], rax
0x18001fcb7  test    byte ptr [rbx+30h], 1
0x18001fcbb  jz      short loc_18001FD2E
0x18001fcbd  mov     rcx, [rbx+48h]
0x18001fcc1  test    rcx, rcx
0x18001fcc4  jz      short loc_18001FD08
0x18001fcc6  mov     rax, [rbx+50h]
0x18001fcca  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x18001fcd1  jnz     short loc_18001FCE0
0x18001fcd3  mov     rax, [rbx+58h]
0x18001fcd7  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x18001fcde  jz      short loc_18001FCFA
0x18001fce0  mov     rax, [rbx+50h]
0x18001fce4  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x18001fceb  jnz     short loc_18001FD2E
0x18001fced  mov     rax, [rbx+58h]
0x18001fcf1  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x18001fcf8  jnz     short loc_18001FD2E
0x18001fcfa  mov     rax, [rcx]
0x18001fcfd  mov     rax, [rax+30h]
0x18001fd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd06  jmp     short loc_18001FD2E
0x18001fd08  test    byte ptr [rbx+64h], 8
0x18001fd0c  jz      short loc_18001FD17
0x18001fd0e  mov     rax, [rbx+80h]
0x18001fd15  jmp     short loc_18001FD24
0x18001fd17  mov     edx, 3
0x18001fd1c  mov     rcx, rbx
0x18001fd1f  call    PGetOemEntrypointAddress
0x18001fd24  test    rax, rax
0x18001fd27  jz      short loc_18001FD2E
0x18001fd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd2e  add     rbx, 0B0h
0x18001fd35  test    esi, esi
0x18001fd37  jnz     loc_18001FC94
0x18001fd3d  mov     rcx, [rdi+0D90h]; hMem
0x18001fd44  test    rcx, rcx
0x18001fd47  jz      short loc_18001FD55
0x18001fd49  call    cs:__imp_LocalFree
0x18001fd50  nop     dword ptr [rax+rax+00h]
0x18001fd55  mov     rcx, [rdi+0D88h]
0x18001fd5c  mov     qword ptr [rdi+0D90h], 0
0x18001fd67  call    VFreeOemPluginInfoInternal
0x18001fd6c  mov     qword ptr [rdi+0D88h], 0
0x18001fd77  mov     rbx, [rsp+28h+arg_0]
0x18001fd7c  mov     rsi, [rsp+28h+arg_8]
0x18001fd81  add     rsp, 20h
0x18001fd85  pop     rdi
0x18001fd86  retn
```

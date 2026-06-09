# dllmain_crt_process_detach(bool)

- ea: `0x1001088e`
- end: `0x10010920`
- name: `?dllmain_crt_process_detach@@YAH_N@Z`
- size: `146`
- prototype: `int __cdecl(__vcrt_bool Terminating)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x10010731`

## callees

- `0x1001088e`
- `0x10010cd2`
- `0x10010d3f`
- `0x10010e0a`
- `0x10010e2d`
- `0x10010fac`
- `0x10010fc9`
- `0x10010ff7`
- `0x10011145`
- `0x10011180`

## pseudocode

```c
BOOL __cdecl dllmain_crt_process_detach(__vcrt_bool Terminating)
{
  int v2; // [esp+0h] [ebp-2Ch]
  int v3; // [esp+4h] [ebp-28h]
  int v4; // [esp+8h] [ebp-24h]
  int v5; // [esp+Ch] [ebp-20h]
  int v6; // [esp+10h] [ebp-1Ch]
  char v7; // [esp+10h] [ebp-1Ch]
  int ms_exc; // [esp+14h] [ebp-18h]
  int ms_exc_4; // [esp+18h] [ebp-14h]
  int ms_exc_8; // [esp+1Ch] [ebp-10h]
  int ms_exc_12; // [esp+20h] [ebp-Ch]
  int ms_exc_16; // [esp+24h] [ebp-8h]

  if ( dword_100349C0 <= 0 )
    return 0;
  --dword_100349C0;
  LOBYTE(v6) = __scrt_acquire_startup_lock();
  if ( dword_10034CF0 != 2 )
  {
    __scrt_fastfail(7);
    __debugbreak();
  }
  __scrt_dllmain_uninitialize_c();
  sub_10010CD2();
  sub_10011145();
  dword_10034CF0 = 0;
  sub_10010E2D(268503268, v2, v3, v4, v5, v6, ms_exc, ms_exc_4, ms_exc_8, ms_exc_12, ms_exc_16, -2);
  __scrt_release_startup_lock(v7);
  return (unsigned __int8)__scrt_uninitialize_crt(Terminating, 0) != 0;
}

```

## disassembly

```asm
0x1001088e  push    0Ch
0x10010890  push    offset stru_10030F60
0x10010895  call    __SEH_prolog4
0x1001089a  mov     eax, dword_100349C0
0x1001089f  test    eax, eax
0x100108a1  jg      short loc_100108A7
0x100108a3  xor     eax, eax
0x100108a5  jmp     short loc_100108F9
0x100108a7  dec     eax
0x100108a8  mov     dword_100349C0, eax
0x100108ad  call    ___scrt_acquire_startup_lock
0x100108b2  mov     byte ptr [ebp+var_1C], al
0x100108b5  and     [ebp+ms_exc.registration.TryLevel], 0
0x100108b9  cmp     dword_10034CF0, 2
0x100108c0  jnz     short loc_10010918
0x100108c2  call    ___scrt_dllmain_uninitialize_c
0x100108c7  call    sub_10010CD2
0x100108cc  call    sub_10011145
0x100108d1  and     dword_10034CF0, 0
0x100108d8  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100108df  call    loc_10010909
0x100108e4  push    0; char
0x100108e6  push    dword ptr [ebp+Terminating]; Terminating
0x100108e9  call    ___scrt_uninitialize_crt
0x100108ee  pop     ecx
0x100108ef  pop     ecx
0x100108f0  xor     ecx, ecx
0x100108f2  test    al, al
0x100108f4  setnz   cl
0x100108f7  mov     eax, ecx
0x100108f9  mov     ecx, [ebp+ms_exc.registration.Next]
0x100108fc  mov     large fs:0, ecx
0x10010903  pop     ecx
0x10010904  pop     edi
0x10010905  pop     esi
0x10010906  pop     ebx
0x10010907  leave
0x10010908  retn
0x10010909  call    sub_10010E2D
0x1001090e  push    [ebp+var_1C]
0x10010911  call    ___scrt_release_startup_lock
0x10010916  pop     ecx
0x10010917  retn
0x10010918  push    7
0x1001091a  call    ___scrt_fastfail
0x1001091f  int     3; Trap to Debugger
```

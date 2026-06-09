# midiOutCachePatches

- ea: `0x180019270`
- end: `0x180019320`
- name: `midiOutCachePatches`
- size: `176`
- prototype: `MMRESULT __stdcall(HMIDIOUT hmo, UINT uBank, LPWORD pwpa, UINT fuCache)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001fb58`

## callees

- `0x1800065d0`
- `0x180007560`
- `0x18000c1d0`
- `0x180017aa0`
- `0x180019270`

## pseudocode

```c
MMRESULT __stdcall midiOutCachePatches(HMIDIOUT hmo, UINT uBank, LPWORD pwpa, UINT fuCache)
{
  unsigned __int16 v4; // di
  unsigned __int16 v6; // bp

  v4 = fuCache;
  v6 = uBank;
  if ( !pwpa )
    return 11;
  if ( (fuCache & 0xFFFFFFF8) != 0 )
    return 10;
  ClientUpdatePnpInfo();
  if ( !(unsigned int)ValidateHandle(hmo, 3) && !(unsigned int)ValidateHandle(hmo, 9) )
    return 5;
  if ( *((_DWORD *)hmo - 18) == 3 )
    return midiMessage(hmo, 12, pwpa, v4 | (v6 << 16));
  if ( *((_DWORD *)hmo - 18) != 9 )
    return 5;
  return midiStreamBroadcast(hmo, 12, pwpa, v4 | (v6 << 16));
}

```

## disassembly

```asm
0x180019270  push    rbx
0x180019272  push    rbp
0x180019273  push    rsi
0x180019274  push    rdi
0x180019275  sub     rsp, 28h
0x180019279  mov     edi, r9d
0x18001927c  mov     rsi, r8
0x18001927f  mov     ebp, edx
0x180019281  mov     rbx, rcx
0x180019284  test    r8, r8
0x180019287  jnz     short loc_180019292
0x180019289  lea     eax, [r8+0Bh]
0x18001928d  jmp     loc_180019317
0x180019292  test    edi, 0FFFFFFF8h
0x180019298  jz      short loc_1800192A1
0x18001929a  mov     eax, 0Ah
0x18001929f  jmp     short loc_180019317
0x1800192a1  call    ClientUpdatePnpInfo
0x1800192a6  mov     edx, 3
0x1800192ab  mov     rcx, rbx
0x1800192ae  call    ValidateHandle
0x1800192b3  test    eax, eax
0x1800192b5  jnz     short loc_1800192CD
0x1800192b7  lea     edx, [rax+9]
0x1800192ba  mov     rcx, rbx
0x1800192bd  call    ValidateHandle
0x1800192c2  test    eax, eax
0x1800192c4  jnz     short loc_1800192CD
0x1800192c6  mov     eax, 5
0x1800192cb  jmp     short loc_180019317
0x1800192cd  cmp     dword ptr [rbx-48h], 3
0x1800192d1  jz      short loc_1800192F9
0x1800192d3  cmp     dword ptr [rbx-48h], 9
0x1800192d7  jnz     short loc_1800192C6
0x1800192d9  movzx   ecx, bp
0x1800192dc  mov     r8, rsi
0x1800192df  shl     ecx, 10h
0x1800192e2  mov     edx, 0Ch
0x1800192e7  movzx   eax, di
0x1800192ea  or      ecx, eax
0x1800192ec  movsxd  r9, ecx
0x1800192ef  mov     rcx, rbx
0x1800192f2  call    midiStreamBroadcast
0x1800192f7  jmp     short loc_180019317
0x1800192f9  movzx   ecx, bp
0x1800192fc  mov     r8, rsi
0x1800192ff  shl     ecx, 10h
0x180019302  mov     edx, 0Ch
0x180019307  movzx   eax, di
0x18001930a  or      ecx, eax
0x18001930c  movsxd  r9, ecx
0x18001930f  mov     rcx, rbx
0x180019312  call    midiMessage
0x180019317  add     rsp, 28h
0x18001931b  pop     rdi
0x18001931c  pop     rsi
0x18001931d  pop     rbp
0x18001931e  pop     rbx
0x18001931f  retn
```

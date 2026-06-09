# DllMain

- ea: `0x18001bc58`
- end: `0x18001bc89`
- name: `DllMain`
- size: `49`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012ed4`

## callees

- `0x18000bd18`
- `0x18000bd50`
- `0x18001bc58`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rax
  bool v4; // sf

  if ( !fdwReason )
  {
    v3 = McGenEventUnregister_EventUnregister(hinstDLL, fdwReason, lpvReserved);
    goto LABEL_7;
  }
  if ( fdwReason != 1 )
  {
LABEL_7:
    LOBYTE(v3) = 1;
    return v3;
  }
  LODWORD(v3) = McGenEventRegister_EventRegister(hinstDLL, fdwReason, lpvReserved);
  v4 = (int)v3 < 0;
  if ( (int)v3 > 0 )
  {
    LODWORD(v3) = (unsigned __int16)v3 | 0x80070000;
    v4 = (int)v3 < 0;
  }
  LOBYTE(v3) = !v4;
  return v3;
}

```

## disassembly

```asm
0x18001bc58  sub     rsp, 28h
0x18001bc5c  test    edx, edx
0x18001bc5e  jz      short loc_18001BC7D
0x18001bc60  cmp     edx, 1
0x18001bc63  jnz     short loc_18001BC82
0x18001bc65  call    McGenEventRegister_EventRegister
0x18001bc6a  test    eax, eax
0x18001bc6c  jle     short loc_18001BC78
0x18001bc6e  movzx   eax, ax
0x18001bc71  or      eax, 80070000h
0x18001bc76  test    eax, eax
0x18001bc78  setns   al
0x18001bc7b  jmp     short loc_18001BC84
0x18001bc7d  call    McGenEventUnregister_EventUnregister
0x18001bc82  mov     al, 1
0x18001bc84  add     rsp, 28h
0x18001bc88  retn
```

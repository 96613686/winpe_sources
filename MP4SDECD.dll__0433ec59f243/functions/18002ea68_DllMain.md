# DllMain

- ea: `0x18002ea68`
- end: `0x18002eabe`
- name: `DllMain`
- size: `86`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002a934`

## callees

- `0x18002575c`
- `0x18002ea68`
- `0x1800456c8`
- `0x180045700`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  int v4; // edx
  __int64 v5; // rcx

  if ( fdwReason )
  {
    v3 = fdwReason - 1;
    if ( !(_DWORD)v3 )
    {
      g_hInst = hinstDLL;
      McGenEventRegister_EventRegister(hinstDLL, v3, lpvReserved);
      v5 = 1;
      goto LABEL_8;
    }
    v4 = v3 - 1;
    if ( !v4 )
    {
      v5 = 2;
      goto LABEL_8;
    }
    if ( v4 == 1 )
    {
      v5 = 3;
LABEL_8:
      DllInitCodec(v5);
    }
  }
  else if ( !lpvReserved )
  {
    DllInitCodec(0);
    McGenEventUnregister_EventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18002ea68  sub     rsp, 28h
0x18002ea6c  test    edx, edx
0x18002ea6e  jz      short loc_18002EAA3
0x18002ea70  sub     edx, 1
0x18002ea73  jz      short loc_18002EA8B
0x18002ea75  sub     edx, 1
0x18002ea78  jz      short loc_18002EA84
0x18002ea7a  cmp     edx, 1
0x18002ea7d  jnz     short loc_18002EAB4
0x18002ea7f  lea     ecx, [rdx+2]
0x18002ea82  jmp     short loc_18002EA9C
0x18002ea84  mov     ecx, 2
0x18002ea89  jmp     short loc_18002EA9C
0x18002ea8b  mov     cs:?g_hInst@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_hInst
0x18002ea92  call    McGenEventRegister_EventRegister
0x18002ea97  mov     ecx, 1
0x18002ea9c  call    DllInitCodec
0x18002eaa1  jmp     short loc_18002EAB4
0x18002eaa3  test    r8, r8
0x18002eaa6  jnz     short loc_18002EAB4
0x18002eaa8  xor     ecx, ecx
0x18002eaaa  call    DllInitCodec
0x18002eaaf  call    McGenEventUnregister_EventUnregister
0x18002eab4  mov     eax, 1
0x18002eab9  add     rsp, 28h
0x18002eabd  retn
```

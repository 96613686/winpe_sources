# DllMain

- ea: `0x10040db20`
- end: `0x10040db61`
- name: `DllMain`
- size: `65`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100468db4`

## callees

- `0x10040db20`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ecx
  _BOOL8 v4; // rdx

  if ( fdwReason != 1 )
    return 1;
  v3 = 0;
  v4 = g_SOSClerk != 0;
  if ( (g_SOSHost != 0) == v4 )
    return v4 == (g_SOSMemObj != 0);
  return v3;
}

```

## disassembly

```asm
0x10040db20  cmp     edx, 1
0x10040db23  jnz     short loc_10040DB5B
0x10040db25  xor     ecx, ecx
0x10040db27  cmp     cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A, rcx; SOS_AutoMemClerk g_SOSClerk
0x10040db2e  mov     eax, ecx
0x10040db30  mov     edx, ecx
0x10040db32  setnz   dl
0x10040db35  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rax; SOS_AutoHost g_SOSHost
0x10040db3c  setnz   al
0x10040db3f  cmp     eax, edx
0x10040db41  jnz     short loc_10040DB58
0x10040db43  mov     eax, ecx
0x10040db45  cmp     cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A, rax; SOS_AutoMemObj g_SOSMemObj
0x10040db4c  setnz   al
0x10040db4f  cmp     edx, eax
0x10040db51  jnz     short loc_10040DB58
0x10040db53  mov     ecx, 1
0x10040db58  mov     eax, ecx
0x10040db5a  retn
0x10040db5b  mov     eax, 1
0x10040db60  retn
```

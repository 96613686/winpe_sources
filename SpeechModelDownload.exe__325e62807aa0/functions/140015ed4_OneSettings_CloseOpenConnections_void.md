# OneSettings::CloseOpenConnections(void)

- ea: `0x140015ed4`
- end: `0x140015f3c`
- name: `?CloseOpenConnections@OneSettings@@AEAAJXZ`
- size: `104`
- prototype: `__int64 __fastcall(OneSettings *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140018534`
- `0x14001a448`

## callees

- `0x140015ed4`

## import_xrefs

- `WINHTTP!WinHttpCloseHandle` at `0x140015ee9`
- `WINHTTP!WinHttpCloseHandle` at `0x140015f06`
- `WINHTTP!WinHttpCloseHandle` at `0x140015f23`
- `WINHTTP!WinHttpCloseHandle` at `0x140015ee9`
- `WINHTTP!WinHttpCloseHandle` at `0x140015f06`
- `WINHTTP!WinHttpCloseHandle` at `0x140015f23`

## pseudocode

```c
__int64 __fastcall OneSettings::CloseOpenConnections(OneSettings *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 23);
  if ( v2 )
  {
    WinHttpCloseHandle(v2);
    *((_QWORD *)this + 23) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 22);
  if ( v3 )
  {
    WinHttpCloseHandle(v3);
    *((_QWORD *)this + 22) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 21);
  if ( v4 )
  {
    WinHttpCloseHandle(v4);
    *((_QWORD *)this + 21) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140015ed4  push    rbx
0x140015ed6  sub     rsp, 20h
0x140015eda  mov     rbx, rcx
0x140015edd  mov     rcx, [rcx+0B8h]; hInternet
0x140015ee4  test    rcx, rcx
0x140015ee7  jz      short loc_140015EFA
0x140015ee9  call    cs:__imp_WinHttpCloseHandle
0x140015eef  mov     qword ptr [rbx+0B8h], 0
0x140015efa  mov     rcx, [rbx+0B0h]; hInternet
0x140015f01  test    rcx, rcx
0x140015f04  jz      short loc_140015F17
0x140015f06  call    cs:__imp_WinHttpCloseHandle
0x140015f0c  mov     qword ptr [rbx+0B0h], 0
0x140015f17  mov     rcx, [rbx+0A8h]; hInternet
0x140015f1e  test    rcx, rcx
0x140015f21  jz      short loc_140015F34
0x140015f23  call    cs:__imp_WinHttpCloseHandle
0x140015f29  mov     qword ptr [rbx+0A8h], 0
0x140015f34  xor     eax, eax
0x140015f36  add     rsp, 20h
0x140015f3a  pop     rbx
0x140015f3b  retn
```

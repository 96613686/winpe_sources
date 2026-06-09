# DeleteReadWriteLock

- ea: `0x180007f70`
- end: `0x180008044`
- name: `DeleteReadWriteLock`
- size: `212`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007f70`
- `0x180008ff0`
- `0x180009130`
- `0x18000b734`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007fb3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007fb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007fa0`

## pseudocode

```c
void __fastcall DeleteReadWriteLock(__int64 a1)
{
  PVOID *v2; // rcx
  void *v3; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 )
      WPP_SF_q(v2[2], 16, WPP_ae89183a349339de188038c4f0a19280_Traceguids, a1);
  }
  v3 = *(void **)(a1 + 56);
  if ( v3 )
  {
    CloseHandle(v3);
    *(_QWORD *)(a1 + 56) = 0;
  }
  if ( *(_DWORD *)(a1 + 4) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    *(_DWORD *)(a1 + 4) = 0;
  }
  *(_DWORD *)(a1 + 48) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
}

```

## disassembly

```asm
0x180007f70  mov     [rsp+arg_0], rbx
0x180007f75  mov     [rsp+arg_8], rsi
0x180007f7a  push    rdi
0x180007f7b  sub     rsp, 20h
0x180007f7f  mov     rbx, rcx
0x180007f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f89  lea     rsi, WPP_GLOBAL_Control
0x180007f90  cmp     rcx, rsi
0x180007f93  jnz     short loc_180007FDB
0x180007f95  mov     rcx, [rbx+38h]; hObject
0x180007f99  xor     edi, edi
0x180007f9b  test    rcx, rcx
0x180007f9e  jz      short loc_180007FAA
0x180007fa0  call    cs:__imp_CloseHandle
0x180007fa6  mov     [rbx+38h], rdi
0x180007faa  cmp     [rbx+4], edi
0x180007fad  jz      short loc_180007FBC
0x180007faf  lea     rcx, [rbx+8]; lpCriticalSection
0x180007fb3  call    cs:__imp_DeleteCriticalSection
0x180007fb9  mov     [rbx+4], edi
0x180007fbc  mov     [rbx+30h], edi
0x180007fbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fc6  cmp     rcx, rsi
0x180007fc9  jnz     short loc_180008006
0x180007fcb  mov     rbx, [rsp+28h+arg_0]
0x180007fd0  mov     rsi, [rsp+28h+arg_8]
0x180007fd5  add     rsp, 20h
0x180007fd9  pop     rdi
0x180007fda  retn
0x180007fdb  test    byte ptr [rcx+1Ch], 8
0x180007fdf  jnz     short loc_180008026
0x180007fe1  cmp     rcx, rsi
0x180007fe4  jz      short loc_180007F95
0x180007fe6  test    byte ptr [rcx+1Ch], 2
0x180007fea  jz      short loc_180007F95
0x180007fec  mov     rcx, [rcx+10h]
0x180007ff0  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180007ff7  mov     edx, 10h
0x180007ffc  mov     r9, rbx
0x180007fff  call    WPP_SF_q
0x180008004  jmp     short loc_180007F95
0x180008006  test    byte ptr [rcx+1Ch], 8
0x18000800a  jz      short loc_180007FCB
0x18000800c  mov     rcx, [rcx+10h]
0x180008010  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180008017  mov     edx, 11h
0x18000801c  xor     r9d, r9d
0x18000801f  call    WPP_SF_L
0x180008024  jmp     short loc_180007FCB
0x180008026  mov     rcx, [rcx+10h]
0x18000802a  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x180008031  mov     edx, 0Fh
0x180008036  call    WPP_SF_
0x18000803b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008042  jmp     short loc_180007FE1
```

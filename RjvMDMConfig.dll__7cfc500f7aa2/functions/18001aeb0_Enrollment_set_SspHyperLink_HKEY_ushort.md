# Enrollment::set_SspHyperLink(HKEY__ *,ushort *)

- ea: `0x18001aeb0`
- end: `0x18001afb5`
- name: `?set_SspHyperLink@Enrollment@@QEAAJPEAUHKEY__@@PEAG@Z`
- size: `261`
- prototype: `int(Enrollment *__hidden this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180017ed8`

## callees

- `0x18001aeb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001af4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001af4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001af3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001af3b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aef7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001af98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aef7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001af98`

## string_xrefs

- `0x18001aed1`: `SSPHyperLink`
- `0x18001af7d`: `SSPHyperLink`

## pseudocode

```c
__int64 __fastcall Enrollment::set_SspHyperLink(Enrollment *this, HKEY a2, unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v7; // ebx
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rax
  SIZE_T dwBytes; // [rsp+88h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  ValueW = RegGetValueW(a2, a3, L"SSPHyperLink", 2u, 0, 0, (LPDWORD)&dwBytes);
  v7 = ValueW;
  if ( ValueW == 2 )
  {
    *((_QWORD *)this + 229) = 0;
    return 0;
  }
  if ( !ValueW )
  {
    v9 = dwBytes;
    ProcessHeap = GetProcessHeap();
    pvData = HeapAlloc(ProcessHeap, 0, v9);
    *((_QWORD *)this + 229) = pvData;
    if ( !pvData )
      return (unsigned int)-2147024882;
    v7 = 0;
    ValueW = RegGetValueW(a2, a3, L"SSPHyperLink", 2u, 0, pvData, (LPDWORD)&dwBytes);
    if ( !ValueW )
      return v7;
    if ( ValueW <= 0 )
      return (unsigned int)ValueW;
    return (unsigned __int16)ValueW | 0x80070000;
  }
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return v7;
}

```

## disassembly

```asm
0x18001aeb0  mov     r11, rsp
0x18001aeb3  push    rbx
0x18001aeb4  push    rbp
0x18001aeb5  push    rsi
0x18001aeb6  push    rdi
0x18001aeb7  sub     rsp, 48h
0x18001aebb  mov     rsi, r8
0x18001aebe  mov     dword ptr [r11+20h], 0
0x18001aec6  mov     rbp, rdx
0x18001aec9  lea     rax, [r11+20h]
0x18001aecd  mov     [r11-38h], rax
0x18001aed1  lea     r8, aSsphyperlink; "SSPHyperLink"
0x18001aed8  mov     rdi, rcx
0x18001aedb  mov     qword ptr [r11-40h], 0
0x18001aee3  mov     r9d, 2; dwFlags
0x18001aee9  mov     qword ptr [r11-48h], 0
0x18001aef1  mov     rdx, rsi; lpSubKey
0x18001aef4  mov     rcx, rbp; hkey
0x18001aef7  call    cs:__imp_RegGetValueW
0x18001aefe  nop     dword ptr [rax+rax+00h]
0x18001af03  mov     ebx, eax
0x18001af05  cmp     eax, 2
0x18001af08  jnz     short loc_18001AF19
0x18001af0a  mov     qword ptr [rdi+728h], 0
0x18001af15  xor     eax, eax
0x18001af17  jmp     short loc_18001AF2A
0x18001af19  test    eax, eax
0x18001af1b  jz      short loc_18001AF34
0x18001af1d  jle     short loc_18001AF28
0x18001af1f  movzx   ebx, ax
0x18001af22  or      ebx, 80070000h
0x18001af28  mov     eax, ebx
0x18001af2a  add     rsp, 48h
0x18001af2e  pop     rdi
0x18001af2f  pop     rsi
0x18001af30  pop     rbp
0x18001af31  pop     rbx
0x18001af32  retn
0x18001af34  mov     ebx, dword ptr [rsp+68h+dwBytes]
0x18001af3b  call    cs:__imp_GetProcessHeap
0x18001af42  nop     dword ptr [rax+rax+00h]
0x18001af47  mov     r8d, ebx; dwBytes
0x18001af4a  xor     edx, edx; dwFlags
0x18001af4c  mov     rcx, rax; hHeap
0x18001af4f  call    cs:__imp_HeapAlloc
0x18001af56  nop     dword ptr [rax+rax+00h]
0x18001af5b  mov     [rdi+728h], rax
0x18001af62  test    rax, rax
0x18001af65  jnz     short loc_18001AF6E
0x18001af67  mov     ebx, 8007000Eh
0x18001af6c  jmp     short loc_18001AF28
0x18001af6e  xor     ebx, ebx
0x18001af70  lea     rcx, [rsp+68h+dwBytes]
0x18001af78  mov     [rsp+68h+pcbData], rcx; pcbData
0x18001af7d  lea     r8, aSsphyperlink; "SSPHyperLink"
0x18001af84  mov     [rsp+68h+pvData], rax; pvData
0x18001af89  mov     rdx, rsi; lpSubKey
0x18001af8c  mov     rcx, rbp; hkey
0x18001af8f  mov     [rsp+68h+pdwType], rbx; pdwType
0x18001af94  lea     r9d, [rbx+2]; dwFlags
0x18001af98  call    cs:__imp_RegGetValueW
0x18001af9f  nop     dword ptr [rax+rax+00h]
0x18001afa4  test    eax, eax
0x18001afa6  jz      short loc_18001AF28
0x18001afa8  jg      loc_18001AF1F
0x18001afae  mov     ebx, eax
0x18001afb0  jmp     loc_18001AF28
```

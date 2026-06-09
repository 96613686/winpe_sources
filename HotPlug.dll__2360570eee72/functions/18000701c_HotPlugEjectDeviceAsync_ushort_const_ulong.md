# HotPlugEjectDeviceAsync(ushort const *,ulong)

- ea: `0x18000701c`
- end: `0x180007126`
- name: `?HotPlugEjectDeviceAsync@@YAKPEBGK@Z`
- size: `266`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800073b0`

## callees

- `0x18000701c`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x1800070ab`
- `KERNEL32!GetModuleHandleExW` at `0x1800070ab`
- `KERNEL32!CloseHandle` at `0x1800070e5`
- `KERNEL32!CloseHandle` at `0x1800070e5`
- `KERNEL32!CreateThread` at `0x1800070cd`
- `KERNEL32!CreateThread` at `0x1800070cd`
- `KERNEL32!FreeLibrary` at `0x1800070fc`
- `KERNEL32!FreeLibrary` at `0x1800070fc`
- `KERNEL32!LocalFree` at `0x180007111`
- `KERNEL32!LocalFree` at `0x180007111`
- `KERNEL32!LocalAlloc` at `0x180007040`
- `KERNEL32!LocalAlloc` at `0x180007040`

## pseudocode

```c
__int64 __fastcall HotPlugEjectDeviceAsync(const unsigned __int16 *a1, int a2)
{
  char *v4; // rax
  void *v5; // rdi
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  char *v9; // rcx
  HANDLE v10; // rax
  DWORD ThreadId; // [rsp+60h] [rbp+18h] BYREF
  HMODULE phModule; // [rsp+68h] [rbp+20h] BYREF

  ThreadId = 0;
  phModule = 0;
  v4 = (char *)LocalAlloc(0x40u, 0x194u);
  v5 = v4;
  if ( !v4 )
    return 19;
  *((_DWORD *)v4 + 100) = a2;
  v7 = 2147483646;
  v8 = 200;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *(_WORD *)v4 = *a1++;
    v4 += 2;
    --v7;
    --v8;
  }
  while ( v8 );
  v9 = v4 - 2;
  if ( v8 )
    v9 = v4;
  *(_WORD *)v9 = 0;
  if ( !v8 )
  {
    v6 = 19;
LABEL_18:
    LocalFree(v5);
    return v6;
  }
  GetModuleHandleExW(4u, (LPCWSTR)HotPlugEjectDeviceStub, &phModule);
  v10 = CreateThread(0, 0, HotPlugEjectDeviceStub, v5, 0, &ThreadId);
  if ( v10 )
  {
    phModule = 0;
    v6 = 0;
    v5 = 0;
    CloseHandle(v10);
  }
  else
  {
    v6 = 19;
  }
  if ( phModule )
    FreeLibrary(phModule);
  if ( v5 )
    goto LABEL_18;
  return v6;
}

```

## disassembly

```asm
0x18000701c  mov     [rsp+arg_0], rbx
0x180007021  push    rbp
0x180007022  push    rsi
0x180007023  push    rdi
0x180007024  sub     rsp, 30h
0x180007028  xor     ebp, ebp
0x18000702a  mov     esi, edx
0x18000702c  mov     rbx, rcx
0x18000702f  mov     [rsp+48h+ThreadId], ebp
0x180007033  mov     edx, 194h; uBytes
0x180007038  mov     [rsp+48h+phModule], rbp
0x18000703d  lea     ecx, [rbp+40h]; uFlags
0x180007040  call    cs:__imp_LocalAlloc
0x180007046  mov     rdi, rax
0x180007049  test    rax, rax
0x18000704c  jnz     short loc_180007056
0x18000704e  lea     ebx, [rbp+13h]
0x180007051  jmp     loc_180007117
0x180007056  mov     [rax+190h], esi
0x18000705c  mov     ecx, 7FFFFFFEh
0x180007061  mov     edx, 0C8h
0x180007066  test    rcx, rcx
0x180007069  jz      short loc_18000708A
0x18000706b  movzx   r8d, word ptr [rbx]
0x18000706f  test    r8w, r8w
0x180007073  jz      short loc_18000708A
0x180007075  mov     [rax], r8w
0x180007079  add     rbx, 2
0x18000707d  add     rax, 2
0x180007081  dec     rcx
0x180007084  sub     rdx, 1
0x180007088  jnz     short loc_180007066
0x18000708a  test    rdx, rdx
0x18000708d  lea     rcx, [rax-2]
0x180007091  cmovnz  rcx, rax
0x180007095  mov     [rcx], bp
0x180007098  jz      short loc_180007109
0x18000709a  lea     r8, [rsp+48h+phModule]; phModule
0x18000709f  mov     ecx, 4; dwFlags
0x1800070a4  lea     rdx, ?HotPlugEjectDeviceStub@@YAKPEAX@Z; lpModuleName
0x1800070ab  call    cs:__imp_GetModuleHandleExW
0x1800070b1  lea     rax, [rsp+48h+ThreadId]
0x1800070b6  mov     r9, rdi; lpParameter
0x1800070b9  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1800070be  lea     r8, ?HotPlugEjectDeviceStub@@YAKPEAX@Z; lpStartAddress
0x1800070c5  xor     edx, edx; dwStackSize
0x1800070c7  mov     [rsp+48h+dwCreationFlags], ebp; dwCreationFlags
0x1800070cb  xor     ecx, ecx; lpThreadAttributes
0x1800070cd  call    cs:__imp_CreateThread
0x1800070d3  test    rax, rax
0x1800070d6  jz      short loc_1800070ED
0x1800070d8  mov     rcx, rax; hObject
0x1800070db  mov     [rsp+48h+phModule], rbp
0x1800070e0  mov     ebx, ebp
0x1800070e2  mov     rdi, rbp
0x1800070e5  call    cs:__imp_CloseHandle
0x1800070eb  jmp     short loc_1800070F2
0x1800070ed  mov     ebx, 13h
0x1800070f2  mov     rcx, [rsp+48h+phModule]; hLibModule
0x1800070f7  test    rcx, rcx
0x1800070fa  jz      short loc_180007102
0x1800070fc  call    cs:__imp_FreeLibrary
0x180007102  test    rdi, rdi
0x180007105  jz      short loc_180007117
0x180007107  jmp     short loc_18000710E
0x180007109  mov     ebx, 13h
0x18000710e  mov     rcx, rdi; hMem
0x180007111  call    cs:__imp_LocalFree
0x180007117  mov     eax, ebx
0x180007119  mov     rbx, [rsp+48h+arg_0]
0x18000711e  add     rsp, 30h
0x180007122  pop     rdi
0x180007123  pop     rsi
0x180007124  pop     rbp
0x180007125  retn
```

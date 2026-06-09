# CreateMMClass(void)

- ea: `0x18001db94`
- end: `0x18001dc70`
- name: `?CreateMMClass@@YAHXZ`
- size: `220`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001dc78`

## callees

- `0x18001102a`
- `0x1800118d0`
- `0x18001db94`

## import_xrefs

- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18001dc0a`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18001dc0a`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x18001dc4f`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x18001dc4f`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassInfoA` at `0x18001dbea`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetClassInfoA` at `0x18001dbea`

## pseudocode

```c
__int64 CreateMMClass(void)
{
  __int64 result; // rax
  tagWNDCLASSA WndClass; // [rsp+20h] [rbp-50h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  if ( classcreated )
    return 1;
  if ( !(unsigned __int8)IsRegisterClassWPresent() )
    return 0;
  if ( GetClassInfoA(ghInst, (LPCSTR)0x2C, &WndClass) )
  {
    if ( WndClass.lpfnWndProc != mmWndProc )
      UnregisterClassA((LPCSTR)0x2C, ghInst);
  }
  WndClass.hInstance = ghInst;
  *(_OWORD *)&WndClass.hIcon = 0;
  *(_QWORD *)&WndClass.style = 0x4000;
  WndClass.lpszMenuName = 0;
  WndClass.lpszClassName = (LPCSTR)44;
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.lpfnWndProc = mmWndProc;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  result = RegisterClassA(&WndClass);
  classcreated = (unsigned __int16)result;
  return result;
}

```

## disassembly

```asm
0x18001db94  mov     [rsp-8+arg_0], rsi
0x18001db99  mov     [rsp-8+arg_8], rdi
0x18001db9e  push    rbp
0x18001db9f  mov     rbp, rsp
0x18001dba2  sub     rsp, 70h
0x18001dba6  xor     edx, edx; Val
0x18001dba8  lea     rcx, [rbp+WndClass]; void *
0x18001dbac  lea     r8d, [rdx+48h]; Size
0x18001dbb0  call    memset_0
0x18001dbb5  cmp     cs:?classcreated@@3HA, 0; int classcreated
0x18001dbbc  jz      short loc_18001DBC8
0x18001dbbe  mov     eax, 1
0x18001dbc3  jmp     loc_18001DC5E
0x18001dbc8  call    IsRegisterClassWPresent
0x18001dbcd  test    al, al
0x18001dbcf  jnz     short loc_18001DBD8
0x18001dbd1  xor     eax, eax
0x18001dbd3  jmp     loc_18001DC5E
0x18001dbd8  mov     rcx, cs:ghInst; hInstance
0x18001dbdf  lea     r8, [rbp+WndClass]; lpWndClass
0x18001dbe3  mov     edi, 2Ch ; ','
0x18001dbe8  mov     edx, edi; lpClassName
0x18001dbea  call    cs:__imp_GetClassInfoA
0x18001dbf0  lea     rsi, ?mmWndProc@@YA_JPEAUHWND__@@I_K_J@Z; mmWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001dbf7  test    eax, eax
0x18001dbf9  jz      short loc_18001DC10
0x18001dbfb  cmp     [rbp+WndClass.lpfnWndProc], rsi
0x18001dbff  jz      short loc_18001DC10
0x18001dc01  mov     rdx, cs:ghInst; hInstance
0x18001dc08  mov     ecx, edi; lpClassName
0x18001dc0a  call    cs:__imp_UnregisterClassA
0x18001dc10  mov     rax, cs:ghInst
0x18001dc17  lea     rcx, [rbp+WndClass]; lpWndClass
0x18001dc1b  xorps   xmm0, xmm0
0x18001dc1e  mov     [rbp+WndClass.hInstance], rax
0x18001dc22  movdqa  xmmword ptr [rbp+WndClass.hIcon], xmm0
0x18001dc27  mov     qword ptr [rbp+WndClass.style], 4000h
0x18001dc2f  mov     [rbp+WndClass.lpszMenuName], 0
0x18001dc37  mov     [rbp+WndClass.lpszClassName], rdi
0x18001dc3b  mov     [rbp+WndClass.hbrBackground], 6
0x18001dc43  mov     [rbp+WndClass.lpfnWndProc], rsi
0x18001dc47  mov     qword ptr [rbp+WndClass.cbClsExtra], 0
0x18001dc4f  call    cs:__imp_RegisterClassA
0x18001dc55  movzx   eax, ax
0x18001dc58  mov     cs:?classcreated@@3HA, eax; int classcreated
0x18001dc5e  lea     r11, [rsp+70h+var_s0]
0x18001dc63  mov     rsi, [r11+10h]
0x18001dc67  mov     rdi, [r11+18h]
0x18001dc6b  mov     rsp, r11
0x18001dc6e  pop     rbp
0x18001dc6f  retn
```

# USBSTOR_BuildMiniportDescriptor

- ea: `0x140028258`
- end: `0x14002833b`
- name: `USBSTOR_BuildMiniportDescriptor`
- size: `227`
- prototype: `__int64 __fastcall(__int64, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400232d0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140013d40`
- `0x140028258`

## pseudocode

```c
__int64 __fastcall USBSTOR_BuildMiniportDescriptor(__int64 a1, int *a2, int *a3)
{
  unsigned int v5; // edi
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // ecx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v5 = *a3;
  if ( (unsigned int)*a3 >= 8 )
  {
    if ( v5 >= 0x10 )
    {
      memset(a2, 0, (unsigned int)*a3);
      a2[2] = 5;
      a2[3] = 1310976;
      v8 = 24;
      if ( v5 >= 0x18 )
        *((_BYTE *)a2 + 16) = 0;
      else
        v8 = 16;
      *a2 = v8;
      a2[1] = v8;
      v6 = 0;
      v7 = v8;
    }
    else
    {
      *a2 = 24;
      a2[1] = 24;
      v6 = 0;
      v7 = 8;
    }
  }
  else
  {
    v6 = -1073741808;
    v7 = 0;
  }
  *a3 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x140028258  push    rbx
0x14002825a  push    rsi
0x14002825b  push    rdi
0x14002825c  push    r14
0x14002825e  sub     rsp, 28h
0x140028262  mov     rsi, r8
0x140028265  mov     rbx, rdx
0x140028268  mov     rcx, cs:WPP_GLOBAL_Control
0x14002826f  lea     r14, WPP_GLOBAL_Control
0x140028276  cmp     rcx, r14
0x140028279  jz      short loc_14002829D
0x14002827b  mov     eax, [rcx+2Ch]
0x14002827e  test    al, 10h
0x140028280  jz      short loc_14002829D
0x140028282  cmp     byte ptr [rcx+29h], 4
0x140028286  jb      short loc_14002829D
0x140028288  mov     rcx, [rcx+18h]
0x14002828c  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140028293  mov     edx, 21h ; '!'
0x140028298  call    WPP_SF_
0x14002829d  mov     edi, [rsi]
0x14002829f  cmp     edi, 8
0x1400282a2  jnb     short loc_1400282AD
0x1400282a4  mov     ebx, 0C0000010h
0x1400282a9  xor     eax, eax
0x1400282ab  jmp     short loc_1400282FA
0x1400282ad  cmp     edi, 10h
0x1400282b0  jnb     short loc_1400282C5
0x1400282b2  mov     ecx, 18h
0x1400282b7  xor     eax, eax
0x1400282b9  mov     [rbx], ecx
0x1400282bb  mov     [rbx+4], ecx
0x1400282be  mov     ebx, eax
0x1400282c0  lea     eax, [rcx-10h]
0x1400282c3  jmp     short loc_1400282FA
0x1400282c5  mov     r8, rdi; Size
0x1400282c8  xor     edx, edx; Val
0x1400282ca  mov     rcx, rbx; void *
0x1400282cd  call    memset
0x1400282d2  xor     eax, eax
0x1400282d4  mov     dword ptr [rbx+8], 5
0x1400282db  mov     dword ptr [rbx+0Ch], 140100h
0x1400282e2  lea     ecx, [rax+18h]
0x1400282e5  cmp     edi, ecx
0x1400282e7  jnb     short loc_1400282EE
0x1400282e9  lea     ecx, [rax+10h]
0x1400282ec  jmp     short loc_1400282F1
0x1400282ee  mov     [rbx+10h], al
0x1400282f1  mov     [rbx], ecx
0x1400282f3  mov     [rbx+4], ecx
0x1400282f6  mov     ebx, eax
0x1400282f8  mov     eax, ecx
0x1400282fa  mov     [rsi], eax
0x1400282fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140028303  cmp     rcx, r14
0x140028306  jz      short loc_14002832E
0x140028308  mov     edx, [rcx+2Ch]
0x14002830b  test    dl, 10h
0x14002830e  jz      short loc_14002832E
0x140028310  cmp     byte ptr [rcx+29h], 5
0x140028314  jb      short loc_14002832E
0x140028316  mov     rcx, [rcx+18h]
0x14002831a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140028321  mov     edx, 22h ; '"'
0x140028326  mov     r9d, ebx
0x140028329  call    WPP_SF_d
0x14002832e  mov     eax, ebx
0x140028330  add     rsp, 28h
0x140028334  pop     r14
0x140028336  pop     rdi
0x140028337  pop     rsi
0x140028338  pop     rbx
0x140028339  retn
```

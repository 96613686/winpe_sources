# HttpCreateClientSession

- ea: `0x18000a280`
- end: `0x18000a3ac`
- name: `HttpCreateClientSession`
- size: `300`
- prototype: `__int64 __fastcall(int, STRSAFE_LPCWSTR, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004010`
- `0x180004090`
- `0x18000a280`
- `0x18000b080`
- `0x18000c87c`

## pseudocode

```c
__int64 __fastcall HttpCreateClientSession(unsigned int a1, STRSAFE_LPCWSTR a2, __int64 a3, int a4, _QWORD *a5)
{
  unsigned int HandleHelper; // ebx
  ULONG v10; // eax
  int v11; // r8d
  int v13[2]; // [rsp+60h] [rbp-48h] BYREF

  *(_QWORD *)v13 = 0;
  if ( (byte_1800126A3 & 0x20) != 0 )
    WPP_SF_llSqLq(a1, (_DWORD)a2, a3, (unsigned __int16)a1, SBYTE2(a1), (__int64)a2, a3, a4, (char)a5);
  if ( !a5 )
    goto LABEL_4;
  *a5 = 0;
  if ( (a4 & 0xFFFFFFFC) != 0 )
    goto LABEL_4;
  if ( !(unsigned int)HttpIsInitialized(0) )
  {
    HandleHelper = 1114;
    goto LABEL_17;
  }
  v10 = 1;
  if ( (a4 & 1) == 0 )
  {
    v11 = -1072693248;
    v10 = 2;
    if ( a2 )
      v11 = -1071906816;
    goto LABEL_15;
  }
  if ( !a2 || !*a2 || a3 )
  {
LABEL_4:
    HandleHelper = 87;
    goto LABEL_17;
  }
  v11 = -2146435072;
LABEL_15:
  HandleHelper = HttpApiCreateHandleHelper((int)v13, a1, v11, 2, a2, a4, v10, 0, a3, 0, 0);
  if ( !HandleHelper )
  {
    *a5 = *(_QWORD *)v13;
    *(_QWORD *)v13 = 0;
  }
LABEL_17:
  if ( (byte_1800126A3 & 0x20) != 0 )
    WPP_SF_d(1053, 13, WPP_d7d37be12c843e04b49fe410409f6e6f_Traceguids, HandleHelper);
  return HandleHelper;
}

```

## disassembly

```asm
0x18000a280  mov     r11, rsp
0x18000a283  push    rbx
0x18000a284  push    rbp
0x18000a285  push    rsi
0x18000a286  push    rdi
0x18000a287  push    r14
0x18000a289  push    r15
0x18000a28b  sub     rsp, 78h
0x18000a28f  xor     r15d, r15d
0x18000a292  mov     ebp, r9d
0x18000a295  mov     [r11-48h], r15
0x18000a299  mov     r14, r8
0x18000a29c  mov     rsi, rdx
0x18000a29f  mov     ebx, ecx
0x18000a2a1  test    cs:byte_1800126A3, 20h
0x18000a2a8  mov     rdi, [rsp+0A8h+arg_20]
0x18000a2b0  jz      short loc_18000A2D4
0x18000a2b2  mov     [r11-68h], rdi
0x18000a2b6  mov     eax, ecx
0x18000a2b8  mov     [rsp+0A8h+var_70], ebp
0x18000a2bc  mov     [r11-78h], r8
0x18000a2c0  shr     eax, 10h
0x18000a2c3  mov     [r11-80h], rdx
0x18000a2c7  movzx   r9d, bx
0x18000a2cb  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000a2cf  call    WPP_SF_llSqLq
0x18000a2d4  test    rdi, rdi
0x18000a2d7  jnz     short loc_18000A2E3
0x18000a2d9  mov     ebx, 57h ; 'W'
0x18000a2de  jmp     loc_18000A37B
0x18000a2e3  mov     [rdi], r15
0x18000a2e6  test    ebp, 0FFFFFFFCh
0x18000a2ec  jnz     short loc_18000A2D9
0x18000a2ee  xor     ecx, ecx
0x18000a2f0  call    HttpIsInitialized
0x18000a2f5  test    eax, eax
0x18000a2f7  jnz     short loc_18000A300
0x18000a2f9  mov     ebx, 45Ah
0x18000a2fe  jmp     short loc_18000A37B
0x18000a300  mov     eax, 1
0x18000a305  lea     r9d, [rax+1]; int
0x18000a309  test    al, bpl
0x18000a30c  jz      short loc_18000A326
0x18000a30e  test    rsi, rsi
0x18000a311  jz      short loc_18000A2D9
0x18000a313  cmp     [rsi], r15w
0x18000a317  jz      short loc_18000A2D9
0x18000a319  test    r14, r14
0x18000a31c  jnz     short loc_18000A2D9
0x18000a31e  mov     r8d, 80100000h
0x18000a324  jmp     short loc_18000A33B
0x18000a326  test    rsi, rsi
0x18000a329  mov     ecx, 0C01C0000h
0x18000a32e  mov     r8d, 0C0100000h
0x18000a334  mov     eax, r9d
0x18000a337  cmovnz  r8d, ecx; int
0x18000a33b  mov     [rsp+0A8h+var_58], r15; __int64
0x18000a340  lea     rcx, [rsp+0A8h+var_48]; int
0x18000a345  mov     [rsp+0A8h+var_60], r15d; int
0x18000a34a  mov     edx, ebx; int
0x18000a34c  mov     [rsp+0A8h+var_68], r14; __int64
0x18000a351  mov     [rsp+0A8h+var_70], r15d; ULONG
0x18000a356  mov     [rsp+0A8h+var_78], eax; ULONG
0x18000a35a  mov     [rsp+0A8h+var_80], ebp; int
0x18000a35e  mov     [rsp+0A8h+var_88], rsi; STRSAFE_LPCWSTR
0x18000a363  call    HttpApiCreateHandleHelper
0x18000a368  mov     ebx, eax
0x18000a36a  test    eax, eax
0x18000a36c  jnz     short loc_18000A37B
0x18000a36e  mov     rcx, qword ptr [rsp+0A8h+var_48]
0x18000a373  mov     [rdi], rcx
0x18000a376  mov     qword ptr [rsp+0A8h+var_48], r15
0x18000a37b  test    cs:byte_1800126A3, 20h
0x18000a382  jz      short loc_18000A39D
0x18000a384  mov     edx, 0Dh
0x18000a389  lea     r8, WPP_d7d37be12c843e04b49fe410409f6e6f_Traceguids
0x18000a390  mov     ecx, 41Dh
0x18000a395  mov     r9d, ebx
0x18000a398  call    WPP_SF_d
0x18000a39d  mov     eax, ebx
0x18000a39f  add     rsp, 78h
0x18000a3a3  pop     r15
0x18000a3a5  pop     r14
0x18000a3a7  pop     rdi
0x18000a3a8  pop     rsi
0x18000a3a9  pop     rbp
0x18000a3aa  pop     rbx
0x18000a3ab  retn
```

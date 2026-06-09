# PuDbgPrint

- ea: `0x180007234`
- end: `0x18000731d`
- name: `PuDbgPrint`
- size: `233`
- prototype: `__int64 __fastcall(struct _DEBUG_PRINTS *, char *, unsigned int, char *, char *, char)`
- caller_count: `16`
- callee_count: `5`
- tags: ``

## callers

- `0x180003e3c`
- `0x180003f60`
- `0x18000422c`
- `0x1800048a4`
- `0x180005900`
- `0x180005d6c`
- `0x180005f7c`
- `0x180006104`
- `0x1800063b4`
- `0x180006460`
- `0x180006508`
- `0x180006bcc`
- `0x180006e00`
- `0x180007604`
- `0x1800076f0`
- `0x180007fbc`

## callees

- `0x180006ec8`
- `0x180007020`
- `0x180007234`
- `0x1800073dc`
- `0x180008410`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007296`
- `KERNEL32!GetLastError` at `0x180007296`
- `KERNEL32!SetLastError` at `0x1800072e7`
- `KERNEL32!SetLastError` at `0x1800072e7`

## pseudocode

```c
void __fastcall PuDbgPrint(struct _DEBUG_PRINTS *a1, char *a2, int a3, char *a4, char *a5, char a6)
{
  DWORD LastError; // ebx
  char *v11; // [rsp+40h] [rbp-C0h] BYREF
  char *v12[5]; // [rsp+48h] [rbp-B8h] BYREF
  int v13; // [rsp+70h] [rbp-90h]
  __int16 v14; // [rsp+74h] [rbp-8Ch]
  int v15; // [rsp+78h] [rbp-88h]
  char v16; // [rsp+80h] [rbp-80h] BYREF

  v13 = 256;
  v12[4] = &v16;
  v14 = 256;
  v15 = 0;
  v16 = 0;
  LastError = GetLastError();
  v11 = &a6;
  FormatMsgToBuffer(v12, a1, a2, a3, a4, a5, &v11);
  PupOutputMessage(a1, (struct STRA *)v12);
  SetLastError(LastError);
  if ( (_BYTE)v14 )
    BUFFER::FreeMemoryInternal((BUFFER *)v12);
}

```

## disassembly

```asm
0x180007234  push    rbp
0x180007236  push    rbx
0x180007237  push    rsi
0x180007238  push    rdi
0x180007239  push    r14
0x18000723b  push    r15
0x18000723d  lea     rbp, [rsp-98h]
0x180007245  sub     rsp, 198h
0x18000724c  mov     rax, cs:__security_cookie
0x180007253  xor     rax, rsp
0x180007256  mov     [rbp+0C0h+var_40], rax
0x18000725d  lea     rax, [rbp+0C0h+var_140]
0x180007261  mov     [rsp+1C0h+var_150], 100h
0x180007269  mov     [rsp+1C0h+var_158], rax
0x18000726e  mov     r14, r9
0x180007271  mov     esi, r8d
0x180007274  mov     [rsp+1C0h+var_14C], 100h
0x18000727b  mov     rdi, rdx
0x18000727e  mov     [rsp+1C0h+var_148], 0
0x180007286  mov     r15, rcx
0x180007289  mov     [rbp+0C0h+var_140], 0
0x18000728d  mov     [rsp+1C0h+var_180], 0
0x180007296  call    cs:__imp_GetLastError
0x18000729c  mov     rdx, [rbp+0C0h+arg_20]
0x1800072a3  lea     rcx, [rsp+1C0h+var_178]; this
0x1800072a8  mov     ebx, eax
0x1800072aa  mov     r9d, esi; unsigned int
0x1800072ad  lea     rax, [rbp+0C0h+arg_28]
0x1800072b4  mov     r8, rdi; char *
0x1800072b7  mov     [rsp+1C0h+var_180], rax
0x1800072bc  lea     rax, [rsp+1C0h+var_180]
0x1800072c1  mov     [rsp+1C0h+var_190], rax; char **
0x1800072c6  mov     [rsp+1C0h+var_198], rdx; char *
0x1800072cb  mov     rdx, r15; struct _DEBUG_PRINTS *
0x1800072ce  mov     [rsp+1C0h+var_1A0], r14; char *
0x1800072d3  call    ?FormatMsgToBuffer@@YAXPEAVSTRA@@PEAU_DEBUG_PRINTS@@PEBDK22PEAPEAD@Z; FormatMsgToBuffer(STRA *,_DEBUG_PRINTS *,char const *,ulong,char const *,char const *,char * *)
0x1800072d8  lea     rdx, [rsp+1C0h+var_178]; struct STRA *
0x1800072dd  mov     rcx, r15; struct _DEBUG_PRINTS *
0x1800072e0  call    ?PupOutputMessage@@YAXPEAU_DEBUG_PRINTS@@PEAVSTRA@@@Z; PupOutputMessage(_DEBUG_PRINTS *,STRA *)
0x1800072e5  mov     ecx, ebx; dwErrCode
0x1800072e7  call    cs:__imp_SetLastError
0x1800072ed  cmp     byte ptr [rsp+1C0h+var_14C], 0
0x1800072f2  jz      short loc_1800072FE
0x1800072f4  lea     rcx, [rsp+1C0h+var_178]; this
0x1800072f9  call    ?FreeMemoryInternal@BUFFER@@AEAAXXZ; BUFFER::FreeMemoryInternal(void)
0x1800072fe  mov     rcx, [rbp+0C0h+var_40]
0x180007305  xor     rcx, rsp; StackCookie
0x180007308  call    __security_check_cookie
0x18000730d  add     rsp, 198h
0x180007314  pop     r15
0x180007316  pop     r14
0x180007318  pop     rdi
0x180007319  pop     rsi
0x18000731a  pop     rbx
0x18000731b  pop     rbp
0x18000731c  retn
```

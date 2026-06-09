# GetHtmlCharset(IStream *,char * *)

- ea: `0x180006250`
- end: `0x180006328`
- name: `?GetHtmlCharset@@YAJPEAUIStream@@PEAPEAD@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct IStream *, char **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006250`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180006309`
- `KERNEL32!CloseHandle` at `0x180006309`
- `KERNEL32!WaitForSingleObject` at `0x1800062e0`
- `KERNEL32!WaitForSingleObject` at `0x1800062e0`
- `KERNEL32!CreateThread` at `0x1800062c5`
- `KERNEL32!CreateThread` at `0x1800062c5`
- `SHLWAPI!__imp_IStream_Reset` at `0x180006297`
- `SHLWAPI!__imp_IStream_Reset` at `0x180006297`

## pseudocode

```c
__int64 __fastcall GetHtmlCharset(struct IStream *a1, char **a2)
{
  HRESULT v3; // ebx
  HANDLE v4; // rax
  void *v5; // rsi
  _QWORD Parameter[2]; // [rsp+30h] [rbp-28h] BYREF
  char *v8; // [rsp+40h] [rbp-18h]
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF

  ThreadId = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  Parameter[0] = 0;
  v8 = 0;
  Parameter[1] = a1;
  v3 = IStream_Reset(a1);
  if ( v3 >= 0 )
  {
    v4 = CreateThread(0, 0, GetHtmlCharsetThreadEntry, Parameter, 0, &ThreadId);
    v5 = v4;
    if ( v4 )
    {
      WaitForSingleObject(v4, 0xFFFFFFFF);
      if ( SLODWORD(Parameter[0]) >= 0 )
      {
        if ( v8 )
          *a2 = v8;
        else
          v3 = -2147024882;
      }
      else
      {
        v3 = Parameter[0];
      }
      CloseHandle(v5);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180006250  mov     rax, rsp
0x180006253  mov     [rax+10h], rbx
0x180006257  mov     [rax+18h], rsi
0x18000625b  push    rdi
0x18000625c  sub     rsp, 50h
0x180006260  mov     dword ptr [rax+8], 0
0x180006267  mov     rdi, rdx
0x18000626a  test    rcx, rcx
0x18000626d  jz      loc_180006313
0x180006273  test    rdx, rdx
0x180006276  jz      loc_180006313
0x18000627c  mov     qword ptr [rdx], 0
0x180006283  mov     qword ptr [rax-28h], 0
0x18000628b  mov     qword ptr [rax-18h], 0
0x180006293  mov     [rax-20h], rcx
0x180006297  call    cs:__imp_IStream_Reset
0x18000629d  mov     ebx, eax
0x18000629f  test    eax, eax
0x1800062a1  js      short loc_18000630F
0x1800062a3  lea     rax, [rsp+58h+ThreadId]
0x1800062a8  xor     edx, edx; dwStackSize
0x1800062aa  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x1800062af  lea     r9, [rsp+58h+Parameter]; lpParameter
0x1800062b4  lea     r8, ?GetHtmlCharsetThreadEntry@@YAKPEAK@Z; lpStartAddress
0x1800062bb  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x1800062c3  xor     ecx, ecx; lpThreadAttributes
0x1800062c5  call    cs:__imp_CreateThread
0x1800062cb  mov     rsi, rax
0x1800062ce  test    rax, rax
0x1800062d1  jnz     short loc_1800062DA
0x1800062d3  mov     ebx, 8007000Eh
0x1800062d8  jmp     short loc_18000630F
0x1800062da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800062dd  mov     rcx, rsi; hHandle
0x1800062e0  call    cs:__imp_WaitForSingleObject
0x1800062e6  mov     eax, [rsp+58h+Parameter]
0x1800062ea  test    eax, eax
0x1800062ec  jns     short loc_1800062F2
0x1800062ee  mov     ebx, eax
0x1800062f0  jmp     short loc_180006306
0x1800062f2  mov     rax, [rsp+58h+var_18]
0x1800062f7  test    rax, rax
0x1800062fa  jnz     short loc_180006303
0x1800062fc  mov     ebx, 8007000Eh
0x180006301  jmp     short loc_180006306
0x180006303  mov     [rdi], rax
0x180006306  mov     rcx, rsi; hObject
0x180006309  call    cs:__imp_CloseHandle
0x18000630f  mov     eax, ebx
0x180006311  jmp     short loc_180006318
0x180006313  mov     eax, 80070057h
0x180006318  mov     rbx, [rsp+58h+arg_8]
0x18000631d  mov     rsi, [rsp+58h+arg_10]
0x180006322  add     rsp, 50h
0x180006326  pop     rdi
0x180006327  retn
```

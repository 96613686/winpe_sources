# BfCheckAndSwitchTarget

- ea: `0x1400060f0`
- end: `0x140006255`
- name: `BfCheckAndSwitchTarget`
- size: `357`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `9`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140001740`
- `0x140006010`
- `0x140011590`
- `0x1400202f0`
- `0x140020730`
- `0x140020ff0`
- `0x1400217b0`
- `0x140024e50`
- `0x140025780`

## callees

- `0x140001348`
- `0x1400060f0`
- `0x140020f10`

## import_xrefs

- `FLTMGR!FltSetCallbackDataDirty` at `0x140006184`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140006184`
- `FLTMGR!FltGetStreamHandleContext` at `0x14000612a`
- `FLTMGR!FltGetStreamHandleContext` at `0x14000612a`
- `FLTMGR!FltReleaseContext` at `0x140006154`
- `FLTMGR!FltReleaseContext` at `0x140006154`

## pseudocode

```c
__int64 __fastcall BfCheckAndSwitchTarget(PFLT_CALLBACK_DATA Data, __int64 a2, PFLT_CONTEXT *a3, char *a4)
{
  struct _FILE_OBJECT *v6; // rdx
  char v9; // bp
  NTSTATUS StreamHandleContext; // eax
  int v11; // edx
  int v12; // ebx
  __int64 result; // rax
  int v14; // eax
  int v15; // [rsp+38h] [rbp-30h]
  PFLT_CONTEXT Context; // [rsp+78h] [rbp+10h] BYREF

  v6 = *(struct _FILE_OBJECT **)(a2 + 32);
  Context = 0;
  v9 = 0;
  StreamHandleContext = FltGetStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), v6, &Context);
  v12 = StreamHandleContext;
  if ( StreamHandleContext < 0 )
  {
    if ( StreamHandleContext != -1073741275 && StreamHandleContext != -1073741637 )
    {
LABEL_19:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = v12;
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_sDd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          4,
          55,
          (__int64)WPP_529f93b0825532f67776c14f74ba0846_Traceguids,
          (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\utils.c",
          172,
          v15);
      }
      goto LABEL_4;
    }
LABEL_3:
    v12 = 0;
    goto LABEL_4;
  }
  v14 = *((_DWORD *)Context + 20);
  if ( (v14 & 1) == 0 )
  {
    if ( (v14 & 2) == 0 )
      goto LABEL_19;
    goto LABEL_3;
  }
  if ( (unsigned __int8)BfMapShadowFileObjectToReal(
                          *(PFLT_INSTANCE *)(a2 + 24),
                          *(PFILE_OBJECT *)(a2 + 32),
                          Context,
                          (__int64)&Data->Iopb->TargetFileObject,
                          0) )
  {
    FltSetCallbackDataDirty(Data);
    v9 = 1;
    if ( a3 )
    {
      *a3 = Context;
      goto LABEL_11;
    }
  }
LABEL_4:
  if ( Context )
    FltReleaseContext(Context);
  if ( v12 < 0 )
    return (unsigned int)v12;
LABEL_11:
  result = (unsigned int)v12;
  if ( a4 )
    *a4 = v9;
  return result;
}

```

## disassembly

```asm
0x1400060f0  mov     [rsp+arg_0], rbx
0x1400060f5  mov     [rsp+arg_10], rbp
0x1400060fa  push    rsi
0x1400060fb  push    rdi
0x1400060fc  push    r12
0x1400060fe  push    r14
0x140006100  push    r15
0x140006102  sub     rsp, 40h
0x140006106  mov     rdi, rdx
0x140006109  mov     r14, r8
0x14000610c  mov     rdx, [rdx+20h]; FileObject
0x140006110  lea     r8, [rsp+68h+Context]; Context
0x140006115  mov     r15, rcx
0x140006118  xor     r12d, r12d
0x14000611b  mov     rsi, r9
0x14000611e  mov     [rsp+68h+Context], r12
0x140006123  mov     rcx, [rdi+18h]; Instance
0x140006127  xor     bpl, bpl
0x14000612a  call    cs:__imp_FltGetStreamHandleContext
0x140006131  nop     dword ptr [rax+rax+00h]
0x140006136  mov     ebx, eax
0x140006138  test    eax, eax
0x14000613a  jns     short loc_1400061AC
0x14000613c  cmp     eax, 0C0000225h
0x140006141  jnz     loc_1400061EE
0x140006147  mov     ebx, r12d
0x14000614a  mov     rcx, [rsp+68h+Context]; Context
0x14000614f  test    rcx, rcx
0x140006152  jz      short loc_140006160
0x140006154  call    cs:__imp_FltReleaseContext
0x14000615b  nop     dword ptr [rax+rax+00h]
0x140006160  test    ebx, ebx
0x140006162  jns     short loc_1400061A0
0x140006164  mov     eax, ebx
0x140006166  mov     rbx, [rsp+68h+arg_0]
0x14000616b  mov     rbp, [rsp+68h+arg_10]
0x140006173  add     rsp, 40h
0x140006177  pop     r15
0x140006179  pop     r14
0x14000617b  pop     r12
0x14000617d  pop     rdi
0x14000617e  pop     rsi
0x14000617f  retn
0x140006181  mov     rcx, r15; Data
0x140006184  call    cs:__imp_FltSetCallbackDataDirty
0x14000618b  nop     dword ptr [rax+rax+00h]
0x140006190  mov     bpl, 1
0x140006193  test    r14, r14
0x140006196  jz      short loc_14000614A
0x140006198  mov     rax, [rsp+68h+Context]
0x14000619d  mov     [r14], rax
0x1400061a0  mov     eax, ebx
0x1400061a2  test    rsi, rsi
0x1400061a5  jz      short loc_140006166
0x1400061a7  mov     [rsi], bpl
0x1400061aa  jmp     short loc_140006166
0x1400061ac  mov     rcx, [rsp+68h+Context]
0x1400061b1  mov     eax, [rcx+50h]
0x1400061b4  test    al, 1
0x1400061b6  jnz     short loc_1400061BE
0x1400061b8  test    al, 2
0x1400061ba  jnz     short loc_140006147
0x1400061bc  jmp     short loc_1400061FA
0x1400061be  mov     r9, [r15+10h]
0x1400061c2  mov     r8, rcx; Context
0x1400061c5  mov     rdx, [rdi+20h]; FileObject
0x1400061c9  mov     rcx, [rdi+18h]; Instance
0x1400061cd  mov     [rsp+68h+var_40], r12; __int64
0x1400061d2  lea     rax, [r9+8]
0x1400061d6  add     r9, 10h
0x1400061da  mov     [rsp+68h+var_48], rax; __int64
0x1400061df  call    BfMapShadowFileObjectToReal
0x1400061e4  test    al, al
0x1400061e6  jz      loc_14000614A
0x1400061ec  jmp     short loc_140006181
0x1400061ee  cmp     ebx, 0C00000BBh
0x1400061f4  jz      loc_140006147
0x1400061fa  lea     rax, WPP_RECORDER_INITIALIZED
0x140006201  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006208  jz      loc_14000614A
0x14000620e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006215  lea     rax, aOnecoreBaseFsW_0; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14000621c  mov     [rsp+68h+var_30], ebx
0x140006220  mov     r9d, 37h ; '7'
0x140006226  mov     [rsp+68h+var_38], 8ACh
0x14000622e  mov     r8d, 4
0x140006234  mov     [rsp+68h+var_40], rax
0x140006239  mov     dl, 2
0x14000623b  mov     rcx, [rcx+40h]
0x14000623f  lea     rax, WPP_529f93b0825532f67776c14f74ba0846_Traceguids
0x140006246  mov     [rsp+68h+var_48], rax
0x14000624b  call    WPP_RECORDER_SF_sDd
0x140006250  jmp     loc_14000614A
```

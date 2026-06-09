# CTieringEngineTaskHandler::Resume(void)

- ea: `0x1400378c0`
- end: `0x140037937`
- name: `?Resume@CTieringEngineTaskHandler@@UEAAJXZ`
- size: `119`
- prototype: `__int64 __fastcall(CTieringEngineTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x140004a40`
- `0x140004ef0`
- `0x140005420`
- `0x1400378c0`

## string_xrefs

- `0x1400378d5`: `CTieringEngineTaskHandler::Resume`

## pseudocode

```c
__int64 __fastcall CTieringEngineTaskHandler::Resume(CTieringEngineTaskHandler *this)
{
  _BYTE v2[8]; // [rsp+20h] [rbp-18h] BYREF
  int v3; // [rsp+28h] [rbp-10h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineTaskHandler::Resume";
  CHResultImp::CHResultImp((CHResultImp *)v2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids);
  }
  v3 = 0;
  CHResultImp::~CHResultImp((CHResultImp *)v2);
  return 0;
}

```

## disassembly

```asm
0x1400378c0  sub     rsp, 38h
0x1400378c4  mov     rax, gs:58h
0x1400378cd  mov     edx, 8
0x1400378d2  mov     rcx, [rax]
0x1400378d5  lea     rax, aCtieringengine_10; "CTieringEngineTaskHandler::Resume"
0x1400378dc  mov     [rdx+rcx], rax
0x1400378e0  lea     rcx, [rsp+38h+var_18]; this
0x1400378e5  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x1400378ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400378f1  lea     rax, WPP_GLOBAL_Control
0x1400378f8  cmp     rcx, rax
0x1400378fb  jz      short loc_14003791E
0x1400378fd  test    byte ptr [rcx+1Ch], 1
0x140037901  jz      short loc_14003791E
0x140037903  cmp     byte ptr [rcx+19h], 4
0x140037907  jb      short loc_14003791E
0x140037909  mov     rcx, [rcx+10h]
0x14003790d  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037914  mov     edx, 1Dh
0x140037919  call    WPP_SF_
0x14003791e  lea     rcx, [rsp+38h+var_18]; this
0x140037923  mov     [rsp+38h+var_10], 0
0x14003792b  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140037930  xor     eax, eax
0x140037932  add     rsp, 38h
0x140037936  retn
```

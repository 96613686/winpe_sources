# CTieringEngineTaskHandler::Stop(long *)

- ea: `0x140037ef0`
- end: `0x140038055`
- name: `?Stop@CTieringEngineTaskHandler@@UEAAJPEAJ@Z`
- size: `357`
- prototype: `__int64 __fastcall(HANDLE *this, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callees

- `0x140004a40`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009f1c`
- `0x140037ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037f71`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140037ff2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140037ff2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140037f67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140037f67`

## string_xrefs

- `0x140037f17`: `CTieringEngineTaskHandler::Stop`

## pseudocode

```c
__int64 __fastcall CTieringEngineTaskHandler::Stop(HANDLE *this, unsigned int *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  _BYTE v7[8]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v8; // [rsp+28h] [rbp-10h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineTaskHandler::Stop";
  CHResultImp::CHResultImp((CHResultImp *)v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, this);
  }
  if ( SetEvent(this[8]) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids);
    }
    WaitForSingleObject(this[10], 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, this);
    }
    *a2 = 0;
    v5 = 0;
    v8 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v8 = v5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, v5);
    }
    *a2 = v5;
  }
  CHResultImp::~CHResultImp((CHResultImp *)v7);
  return v5;
}

```

## disassembly

```asm
0x140037ef0  mov     [rsp+arg_0], rbx
0x140037ef5  mov     [rsp+arg_8], rdi
0x140037efa  push    r14
0x140037efc  sub     rsp, 30h
0x140037f00  mov     rax, gs:58h
0x140037f09  mov     rbx, rcx
0x140037f0c  mov     ecx, 8
0x140037f11  mov     rdi, rdx
0x140037f14  mov     r8, [rax]
0x140037f17  lea     rax, aCtieringengine_9; "CTieringEngineTaskHandler::Stop"
0x140037f1e  mov     [rcx+r8], rax
0x140037f22  lea     rcx, [rsp+38h+var_18]; this
0x140037f27  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140037f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140037f33  lea     r14, WPP_GLOBAL_Control
0x140037f3a  cmp     rcx, r14
0x140037f3d  jz      short loc_140037F63
0x140037f3f  test    byte ptr [rcx+1Ch], 1
0x140037f43  jz      short loc_140037F63
0x140037f45  cmp     byte ptr [rcx+19h], 4
0x140037f49  jb      short loc_140037F63
0x140037f4b  mov     rcx, [rcx+10h]
0x140037f4f  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037f56  mov     edx, 17h
0x140037f5b  mov     r9, rbx
0x140037f5e  call    WPP_SF_q
0x140037f63  mov     rcx, [rbx+40h]; hEvent
0x140037f67  call    cs:__imp_SetEvent
0x140037f6d  test    eax, eax
0x140037f6f  jnz     short loc_140037FBE
0x140037f71  call    cs:__imp_GetLastError
0x140037f77  mov     ebx, eax
0x140037f79  test    eax, eax
0x140037f7b  jle     short loc_140037F86
0x140037f7d  movzx   ebx, ax
0x140037f80  or      ebx, 80070000h
0x140037f86  mov     [rsp+38h+var_10], ebx
0x140037f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037f91  cmp     rcx, r14
0x140037f94  jz      short loc_140037FBA
0x140037f96  test    byte ptr [rcx+1Ch], 1
0x140037f9a  jz      short loc_140037FBA
0x140037f9c  cmp     byte ptr [rcx+19h], 2
0x140037fa0  jb      short loc_140037FBA
0x140037fa2  mov     rcx, [rcx+10h]
0x140037fa6  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037fad  mov     edx, 18h
0x140037fb2  mov     r9d, ebx
0x140037fb5  call    WPP_SF_d
0x140037fba  mov     [rdi], ebx
0x140037fbc  jmp     short loc_140038038
0x140037fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x140037fc5  cmp     rcx, r14
0x140037fc8  jz      short loc_140037FEB
0x140037fca  test    byte ptr [rcx+1Ch], 1
0x140037fce  jz      short loc_140037FEB
0x140037fd0  cmp     byte ptr [rcx+19h], 4
0x140037fd4  jb      short loc_140037FEB
0x140037fd6  mov     rcx, [rcx+10h]
0x140037fda  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037fe1  mov     edx, 19h
0x140037fe6  call    WPP_SF_
0x140037feb  mov     rcx, [rbx+50h]; hHandle
0x140037fef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140037ff2  call    cs:__imp_WaitForSingleObject
0x140037ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x140037fff  cmp     rcx, r14
0x140038002  jz      short loc_140038028
0x140038004  test    byte ptr [rcx+1Ch], 1
0x140038008  jz      short loc_140038028
0x14003800a  cmp     byte ptr [rcx+19h], 4
0x14003800e  jb      short loc_140038028
0x140038010  mov     rcx, [rcx+10h]
0x140038014  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x14003801b  mov     edx, 1Ah
0x140038020  mov     r9, rbx
0x140038023  call    WPP_SF_q
0x140038028  mov     dword ptr [rdi], 0
0x14003802e  xor     ebx, ebx
0x140038030  mov     [rsp+38h+var_10], 0
0x140038038  lea     rcx, [rsp+38h+var_18]; this
0x14003803d  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x140038042  mov     rdi, [rsp+38h+arg_8]
0x140038047  mov     eax, ebx
0x140038049  mov     rbx, [rsp+38h+arg_0]
0x14003804e  add     rsp, 30h
0x140038052  pop     r14
0x140038054  retn
```

# CTieringEngineTaskHandler::Pause(void)

- ea: `0x1400377d0`
- end: `0x1400378b1`
- name: `?Pause@CTieringEngineTaskHandler@@UEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x140004a40`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x1400377d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037845`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003783b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003783b`

## string_xrefs

- `0x1400377ee`: `CTieringEngineTaskHandler::Pause`

## pseudocode

```c
__int64 __fastcall CTieringEngineTaskHandler::Pause(HANDLE *this)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  _BYTE v5[8]; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v6; // [rsp+28h] [rbp-10h]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "CTieringEngineTaskHandler::Pause";
  CHResultImp::CHResultImp((CHResultImp *)v5);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids);
  }
  if ( SetEvent(this[9]) )
  {
    v6 = 0;
    v3 = 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v6 = v3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids, v3);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)v5);
  return v3;
}

```

## disassembly

```asm
0x1400377d0  mov     [rsp+arg_0], rbx
0x1400377d5  push    rdi
0x1400377d6  sub     rsp, 30h
0x1400377da  mov     rax, gs:58h
0x1400377e3  mov     rbx, rcx
0x1400377e6  mov     ecx, 8
0x1400377eb  mov     rdx, [rax]
0x1400377ee  lea     rax, aCtieringengine_7; "CTieringEngineTaskHandler::Pause"
0x1400377f5  mov     [rcx+rdx], rax
0x1400377f9  lea     rcx, [rsp+38h+var_18]; this
0x1400377fe  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x140037803  mov     rcx, cs:WPP_GLOBAL_Control
0x14003780a  lea     rdi, WPP_GLOBAL_Control
0x140037811  cmp     rcx, rdi
0x140037814  jz      short loc_140037837
0x140037816  test    byte ptr [rcx+1Ch], 1
0x14003781a  jz      short loc_140037837
0x14003781c  cmp     byte ptr [rcx+19h], 4
0x140037820  jb      short loc_140037837
0x140037822  mov     rcx, [rcx+10h]
0x140037826  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x14003782d  mov     edx, 1Bh
0x140037832  call    WPP_SF_
0x140037837  mov     rcx, [rbx+48h]; hEvent
0x14003783b  call    cs:__imp_SetEvent
0x140037841  test    eax, eax
0x140037843  jnz     short loc_140037890
0x140037845  call    cs:__imp_GetLastError
0x14003784b  mov     ebx, eax
0x14003784d  test    eax, eax
0x14003784f  jle     short loc_14003785A
0x140037851  movzx   ebx, ax
0x140037854  or      ebx, 80070000h
0x14003785a  mov     [rsp+38h+var_10], ebx
0x14003785e  mov     rcx, cs:WPP_GLOBAL_Control
0x140037865  cmp     rcx, rdi
0x140037868  jz      short loc_14003789A
0x14003786a  test    byte ptr [rcx+1Ch], 1
0x14003786e  jz      short loc_14003789A
0x140037870  cmp     byte ptr [rcx+19h], 2
0x140037874  jb      short loc_14003789A
0x140037876  mov     rcx, [rcx+10h]
0x14003787a  lea     r8, WPP_3a4908e74eb6305e32d135dfcea73d83_Traceguids
0x140037881  mov     edx, 1Ch
0x140037886  mov     r9d, ebx
0x140037889  call    WPP_SF_d
0x14003788e  jmp     short loc_14003789A
0x140037890  mov     [rsp+38h+var_10], 0
0x140037898  xor     ebx, ebx
0x14003789a  lea     rcx, [rsp+38h+var_18]; this
0x14003789f  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1400378a4  mov     eax, ebx
0x1400378a6  mov     rbx, [rsp+38h+arg_0]
0x1400378ab  add     rsp, 30h
0x1400378af  pop     rdi
0x1400378b0  retn
```

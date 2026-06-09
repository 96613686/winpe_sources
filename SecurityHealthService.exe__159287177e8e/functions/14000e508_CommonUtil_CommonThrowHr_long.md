# CommonUtil::CommonThrowHr(long)

- ea: `0x14000e508`
- end: `0x14000e59c`
- name: `?CommonThrowHr@CommonUtil@@YAXJ@Z`
- size: `148`
- prototype: `void __fastcall __noreturn(CommonUtil *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400102f0`

## callees

- `0x140002050`
- `0x140003640`
- `0x14000536c`
- `0x14000e47c`
- `0x14000e508`

## pseudocode

```c
void __fastcall __noreturn CommonUtil::CommonThrowHr(CommonUtil *this)
{
  unsigned int v1; // ebx
  _QWORD *v2; // rcx
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v1 = (unsigned int)this;
  if ( (int)this < 0 )
  {
    v2 = WPP_GLOBAL_Control;
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_c6dcf0e142e334d1d5da235334ca454b_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v1 = -2147418113;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_d(v2[2], 11, WPP_c6dcf0e142e334d1d5da235334ca454b_Traceguids, v1);
  CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl((CommonUtil::CHResultExceptionImpl *)pExceptionObject, v1);
  throw (CommonUtil::CHResultExceptionImpl *)pExceptionObject;
}

```

## disassembly

```asm
0x14000e508  mov     [rsp+arg_8], rbx
0x14000e50d  push    rdi
0x14000e50e  sub     rsp, 50h
0x14000e512  lea     rdi, WPP_GLOBAL_Control
0x14000e519  mov     ebx, ecx
0x14000e51b  test    ecx, ecx
0x14000e51d  js      short loc_14000E554
0x14000e51f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e526  cmp     rcx, rdi
0x14000e529  jz      short loc_14000E54D
0x14000e52b  test    byte ptr [rcx+1Ch], 1
0x14000e52f  jz      short loc_14000E54D
0x14000e531  mov     rcx, [rcx+10h]
0x14000e535  lea     r8, WPP_c6dcf0e142e334d1d5da235334ca454b_Traceguids
0x14000e53c  mov     edx, 0Ah
0x14000e541  call    WPP_SF_
0x14000e546  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e54d  mov     ebx, 8000FFFFh
0x14000e552  jmp     short loc_14000E55B
0x14000e554  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e55b  cmp     rcx, rdi
0x14000e55e  jz      short loc_14000E57E
0x14000e560  test    byte ptr [rcx+1Ch], 1
0x14000e564  jz      short loc_14000E57E
0x14000e566  mov     rcx, [rcx+10h]
0x14000e56a  lea     r8, WPP_c6dcf0e142e334d1d5da235334ca454b_Traceguids
0x14000e571  mov     edx, 0Bh
0x14000e576  mov     r9d, ebx
0x14000e579  call    WPP_SF_d
0x14000e57e  mov     edx, ebx; int
0x14000e580  lea     rcx, [rsp+58h+pExceptionObject]; this
0x14000e585  call    ??0CHResultExceptionImpl@CommonUtil@@QEAA@J@Z; CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(long)
0x14000e58a  lea     rdx, _TI3?AVCHResultExceptionImpl@CommonUtil@@; pThrowInfo
0x14000e591  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x14000e596  call    _CxxThrowException_0
```

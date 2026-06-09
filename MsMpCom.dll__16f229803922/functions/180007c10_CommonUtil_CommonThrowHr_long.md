# CommonUtil::CommonThrowHr(long)

- ea: `0x180007c10`
- end: `0x180007ca4`
- name: `?CommonThrowHr@CommonUtil@@YAXJ@Z`
- size: `148`
- prototype: `void __fastcall __noreturn(CommonUtil *__hidden this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007e24`
- `0x180008a6c`

## callees

- `0x180001ccc`
- `0x180004b54`
- `0x180004b7c`
- `0x180007b60`
- `0x180007c10`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_22aa8ccf2d7836e02b5c9a20467f81c3_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v1 = -2147418113;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_d(v2[2], 11, WPP_22aa8ccf2d7836e02b5c9a20467f81c3_Traceguids, v1);
  CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl((CommonUtil::CHResultExceptionImpl *)pExceptionObject, v1);
  throw (CommonUtil::CHResultExceptionImpl *)pExceptionObject;
}

```

## disassembly

```asm
0x180007c10  mov     [rsp+arg_8], rbx
0x180007c15  push    rdi
0x180007c16  sub     rsp, 50h
0x180007c1a  lea     rdi, WPP_GLOBAL_Control
0x180007c21  mov     ebx, ecx
0x180007c23  test    ecx, ecx
0x180007c25  js      short loc_180007C5C
0x180007c27  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c2e  cmp     rcx, rdi
0x180007c31  jz      short loc_180007C55
0x180007c33  test    byte ptr [rcx+1Ch], 1
0x180007c37  jz      short loc_180007C55
0x180007c39  mov     rcx, [rcx+10h]
0x180007c3d  lea     r8, WPP_22aa8ccf2d7836e02b5c9a20467f81c3_Traceguids
0x180007c44  mov     edx, 0Ah
0x180007c49  call    WPP_SF_
0x180007c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c55  mov     ebx, 8000FFFFh
0x180007c5a  jmp     short loc_180007C63
0x180007c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c63  cmp     rcx, rdi
0x180007c66  jz      short loc_180007C86
0x180007c68  test    byte ptr [rcx+1Ch], 1
0x180007c6c  jz      short loc_180007C86
0x180007c6e  mov     rcx, [rcx+10h]
0x180007c72  lea     r8, WPP_22aa8ccf2d7836e02b5c9a20467f81c3_Traceguids
0x180007c79  mov     edx, 0Bh
0x180007c7e  mov     r9d, ebx
0x180007c81  call    WPP_SF_d
0x180007c86  mov     edx, ebx; int
0x180007c88  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180007c8d  call    ??0CHResultExceptionImpl@CommonUtil@@QEAA@J@Z; CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(long)
0x180007c92  lea     rdx, _TI3?AVCHResultExceptionImpl@CommonUtil@@; pThrowInfo
0x180007c99  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180007c9e  call    _CxxThrowException_0
```

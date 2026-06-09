# CommonUtil::CommonThrowHr(long)

- ea: `0x140002e74`
- end: `0x140002f0d`
- name: `?CommonThrowHr@CommonUtil@@YAXJ@Z`
- size: `153`
- prototype: `void __fastcall __noreturn(CommonUtil *__hidden this, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000309c`
- `0x14000530c`
- `0x14001d464`
- `0x14001e068`
- `0x1400234b0`

## callees

- `0x140002de8`
- `0x140002e74`
- `0x140007c1c`
- `0x14001da4c`
- `0x14001da70`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_429bfe7ee05638f6cdfd4577544f8733_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    v1 = -2147418113;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
    WPP_SF_d(v2[2], 11, WPP_429bfe7ee05638f6cdfd4577544f8733_Traceguids, v1);
  CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl((CommonUtil::CHResultExceptionImpl *)pExceptionObject, v1);
  throw (CommonUtil::CHResultExceptionImpl *)pExceptionObject;
}

```

## disassembly

```asm
0x140002e74  mov     [rsp+arg_0], rbx
0x140002e79  push    rdi
0x140002e7a  sub     rsp, 50h
0x140002e7e  mov     eax, ecx
0x140002e80  lea     rdi, WPP_GLOBAL_Control
0x140002e87  shr     eax, 1Fh
0x140002e8a  mov     ebx, ecx
0x140002e8c  test    al, al
0x140002e8e  jnz     short loc_140002EC5
0x140002e90  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e97  cmp     rcx, rdi
0x140002e9a  jz      short loc_140002EBE
0x140002e9c  test    byte ptr [rcx+1Ch], 1
0x140002ea0  jz      short loc_140002EBE
0x140002ea2  mov     rcx, [rcx+10h]
0x140002ea6  lea     r8, WPP_429bfe7ee05638f6cdfd4577544f8733_Traceguids
0x140002ead  mov     edx, 0Ah
0x140002eb2  call    WPP_SF_
0x140002eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ebe  mov     ebx, 8000FFFFh
0x140002ec3  jmp     short loc_140002ECC
0x140002ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ecc  cmp     rcx, rdi
0x140002ecf  jz      short loc_140002EEF
0x140002ed1  test    byte ptr [rcx+1Ch], 4
0x140002ed5  jz      short loc_140002EEF
0x140002ed7  mov     rcx, [rcx+10h]
0x140002edb  lea     r8, WPP_429bfe7ee05638f6cdfd4577544f8733_Traceguids
0x140002ee2  mov     edx, 0Bh
0x140002ee7  mov     r9d, ebx
0x140002eea  call    WPP_SF_d
0x140002eef  mov     edx, ebx; int
0x140002ef1  lea     rcx, [rsp+58h+pExceptionObject]; this
0x140002ef6  call    ??0CHResultExceptionImpl@CommonUtil@@QEAA@J@Z; CommonUtil::CHResultExceptionImpl::CHResultExceptionImpl(long)
0x140002efb  lea     rdx, _TI3?AVCHResultExceptionImpl@CommonUtil@@; pThrowInfo
0x140002f02  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140002f07  call    _CxxThrowException
```

# CLogStorage::_CommonInit(ulong,int)

- ea: `0x18000afa8`
- end: `0x18000b064`
- name: `?_CommonInit@CLogStorage@@AEAAXKH@Z`
- size: `188`
- prototype: `void __fastcall(CLogStorage *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009e6c`
- `0x18000bc44`

## callees

- `0x18000afa8`
- `0x18000d998`
- `0x18001266c`

## string_xrefs

- `0x18000b032`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
void __fastcall CLogStorage::_CommonInit(CLogStorage *this, int a2, int a3)
{
  int v3; // eax
  unsigned int v4; // edx
  __int64 v5; // r8
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  *((_DWORD *)this + 10) = a2;
  v3 = 4 * a2;
  *((_DWORD *)this + 7) = 0;
  v4 = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 26) = 1;
  *((_DWORD *)this + 31) = 1;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 27) = v3;
  for ( *((_DWORD *)this + 29) = a3; v4 < *((_DWORD *)this + 187); ++v4 )
  {
    v5 = *((_QWORD *)this + 94) + 80LL * v4;
    if ( !v5 )
    {
      TraceFile(-2147024882, "E_OUTOFMEMORY", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x364u);
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    *(_DWORD *)(v5 + 72) = v4;
  }
  *((_QWORD *)this + 95) = 0;
}

```

## disassembly

```asm
0x18000afa8  sub     rsp, 28h
0x18000afac  xor     r10d, r10d
0x18000afaf  mov     [rcx+28h], edx
0x18000afb2  lea     eax, ds:0[rdx*4]
0x18000afb9  mov     [rcx+1Ch], r10d
0x18000afbd  mov     edx, r10d
0x18000afc0  mov     [rcx+50h], r10
0x18000afc4  mov     [rcx+58h], r10
0x18000afc8  lea     r11d, [r10+1]
0x18000afcc  mov     [rcx+40h], r10
0x18000afd0  mov     [rcx+68h], r11d
0x18000afd4  mov     [rcx+7Ch], r11d
0x18000afd8  mov     [rcx+48h], r10
0x18000afdc  mov     [rcx+60h], r10
0x18000afe0  mov     [rcx+80h], r10
0x18000afe7  mov     [rcx+88h], r10
0x18000afee  mov     [rcx+6Ch], eax
0x18000aff1  mov     [rcx+74h], r8d
0x18000aff5  cmp     [rcx+2ECh], r10d
0x18000affc  jbe     short loc_18000B020
0x18000affe  mov     eax, edx
0x18000b000  lea     r8, [rax+rax*4]
0x18000b004  shl     r8, 4
0x18000b008  add     r8, [rcx+2F0h]
0x18000b00f  jz      short loc_18000B02C
0x18000b011  mov     [r8+48h], edx
0x18000b015  add     edx, r11d
0x18000b018  cmp     edx, [rcx+2ECh]
0x18000b01e  jb      short loc_18000AFFE
0x18000b020  mov     [rcx+2F8h], r10
0x18000b027  add     rsp, 28h
0x18000b02b  retn
0x18000b02c  mov     r9d, 364h; unsigned int
0x18000b032  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000b039  lea     rdx, aEOutofmemory; "E_OUTOFMEMORY"
0x18000b040  mov     ecx, 8007000Eh; int
0x18000b045  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000b04a  lea     rdx, _TI1J; pThrowInfo
0x18000b051  mov     [rsp+28h+pExceptionObject], 8007000Eh
0x18000b059  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000b05e  call    _CxxThrowException_0
```

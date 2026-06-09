# _read

- ea: `0x140023ffc`
- end: `0x14002411a`
- name: `_read`
- size: `286`
- prototype: `int __cdecl(int FileHandle, void *DstBuf, unsigned int MaxCharCount)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140020730`
- `0x1400208d4`

## callees

- `0x14001609c`
- `0x140016e7c`
- `0x140016ea0`
- `0x14001e450`
- `0x14001e538`
- `0x140023ffc`
- `0x14002411c`

## pseudocode

```c
int __cdecl read(int FileHandle, void *DstBuf, unsigned int MaxCharCount)
{
  __int64 v6; // rdx
  int v7; // ecx
  BOOL v9; // eax
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // r15
  __int64 v13; // rdx
  int v14; // ecx
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // ebx

  if ( FileHandle == -2 )
  {
    *(_DWORD *)sub_140016E7C() = 0;
    *(_DWORD *)sub_140016EA0(v7, v6) = 9;
    return -1;
  }
  v9 = FileHandle >= 0 && FileHandle < (unsigned int)dword_14003EA00;
  if ( !v9
    || (v12 = (__int64)FileHandle >> 6, (*(_BYTE *)(qword_14003E600[v12] + 72LL * (FileHandle & 0x3F) + 56) & 1) == 0) )
  {
    *(_DWORD *)sub_140016E7C() = 0;
    *(_DWORD *)sub_140016EA0(v11, v10) = 9;
LABEL_10:
    invalid_parameter_noinfo();
    return -1;
  }
  if ( MaxCharCount > 0x7FFFFFFF )
  {
    *(_DWORD *)sub_140016E7C() = 0;
    *(_DWORD *)sub_140016EA0(v14, v13) = 22;
    goto LABEL_10;
  }
  _acrt_lowio_lock_fh((unsigned int)FileHandle);
  v17 = -1;
  if ( (*(_BYTE *)(qword_14003E600[v12] + 72LL * (FileHandle & 0x3F) + 56) & 1) != 0 )
  {
    v17 = sub_14002411C((unsigned int)FileHandle, DstBuf, MaxCharCount);
  }
  else
  {
    *(_DWORD *)sub_140016EA0(v16, v15) = 9;
    *(_DWORD *)sub_140016E7C() = 0;
  }
  _acrt_lowio_unlock_fh(FileHandle);
  return v17;
}

```

## disassembly

```asm
0x140023ffc  mov     rax, rsp
0x140023fff  mov     [rax+10h], rbx
0x140024003  mov     [rax+18h], rsi
0x140024007  mov     [rax+20h], r12
0x14002400b  mov     [rax+8], ecx
0x14002400e  push    r13
0x140024010  push    r14
0x140024012  push    r15
0x140024014  sub     rsp, 20h
0x140024018  mov     r14d, r8d
0x14002401b  mov     r12, rdx
0x14002401e  movsxd  rsi, ecx
0x140024021  cmp     esi, 0FFFFFFFEh
0x140024024  jnz     short loc_140024056
0x140024026  call    sub_140016E7C
0x14002402b  and     dword ptr [rax], 0
0x14002402e  call    sub_140016EA0
0x140024033  mov     dword ptr [rax], 9
0x140024039  or      eax, 0FFFFFFFFh
0x14002403c  mov     rbx, [rsp+38h+arg_8]
0x140024041  mov     rsi, [rsp+38h+arg_10]
0x140024046  mov     r12, [rsp+38h+arg_18]
0x14002404b  add     rsp, 20h
0x14002404f  pop     r15
0x140024051  pop     r14
0x140024053  pop     r13
0x140024055  retn
0x140024056  test    ecx, ecx
0x140024058  js      short loc_140024069
0x14002405a  cmp     esi, cs:dword_14003EA00
0x140024060  jnb     short loc_140024069
0x140024062  mov     eax, 1
0x140024067  jmp     short loc_14002406B
0x140024069  xor     eax, eax
0x14002406b  test    eax, eax
0x14002406d  jnz     short loc_140024089
0x14002406f  call    sub_140016E7C
0x140024074  and     dword ptr [rax], 0
0x140024077  call    sub_140016EA0
0x14002407c  mov     dword ptr [rax], 9
0x140024082  call    _invalid_parameter_noinfo
0x140024087  jmp     short loc_140024039
0x140024089  mov     rax, rsi
0x14002408c  mov     r15, rsi
0x14002408f  sar     r15, 6
0x140024093  lea     rcx, qword_14003E600
0x14002409a  and     eax, 3Fh
0x14002409d  lea     r13, [rax+rax*8]
0x1400240a1  mov     rax, [rcx+r15*8]
0x1400240a5  test    byte ptr [rax+r13*8+38h], 1
0x1400240ab  jz      short loc_14002406F
0x1400240ad  cmp     r14d, 7FFFFFFFh
0x1400240b4  jbe     short loc_1400240CB
0x1400240b6  call    sub_140016E7C
0x1400240bb  and     dword ptr [rax], 0
0x1400240be  call    sub_140016EA0
0x1400240c3  mov     dword ptr [rax], 16h
0x1400240c9  jmp     short loc_140024082
0x1400240cb  mov     ecx, esi
0x1400240cd  call    __acrt_lowio_lock_fh
0x1400240d2  or      ebx, 0FFFFFFFFh
0x1400240d5  lea     rax, qword_14003E600
0x1400240dc  mov     rax, [rax+r15*8]
0x1400240e0  test    byte ptr [rax+r13*8+38h], 1
0x1400240e6  jnz     short loc_1400240FD
0x1400240e8  call    sub_140016EA0
0x1400240ed  mov     dword ptr [rax], 9
0x1400240f3  call    sub_140016E7C
0x1400240f8  and     dword ptr [rax], 0
0x1400240fb  jmp     short loc_14002410C
0x1400240fd  mov     r8d, r14d
0x140024100  mov     rdx, r12
0x140024103  mov     ecx, esi
0x140024105  call    sub_14002411C
0x14002410a  mov     ebx, eax
0x14002410c  mov     ecx, esi
0x14002410e  call    __acrt_lowio_unlock_fh
0x140024113  mov     eax, ebx
0x140024115  jmp     loc_14002403C
0x14002b2f5  push    rbp; Microsoft VisualC 64bit universal runtime
0x14002b2f7  sub     rsp, 20h
0x14002b2fb  mov     rbp, rdx
0x14002b2fe  mov     ecx, [rbp+40h]
0x14002b301  add     rsp, 20h
0x14002b305  pop     rbp
0x14002b306  jmp     __acrt_lowio_unlock_fh
```

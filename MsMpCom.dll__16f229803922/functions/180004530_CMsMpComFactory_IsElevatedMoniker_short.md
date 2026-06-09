# CMsMpComFactory::IsElevatedMoniker(short *)

- ea: `0x180004530`
- end: `0x1800045bb`
- name: `?IsElevatedMoniker@CMsMpComFactory@@UEAAJPEAF@Z`
- size: `139`
- prototype: `__int64 __fastcall(CMsMpComFactory *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004530`
- `0x180004b54`
- `0x18000a010`

## import_xrefs

- `mpclient!MpUtilsExportFunctions` at `0x180004588`
- `mpclient!MpUtilsExportFunctions` at `0x180004588`

## pseudocode

```c
__int64 __fastcall CMsMpComFactory::IsElevatedMoniker(CMsMpComFactory *this, __int16 *a2)
{
  __int64 result; // rax
  __int64 v4; // rax
  __int16 v5; // ax
  int v6; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( *((_BYTE *)this + 32) )
  {
    v6 = 0;
    v4 = MpUtilsExportFunctions();
    result = (*(__int64 (__fastcall **)(_QWORD, int *))(v4 + 96))(0, &v6);
    if ( (int)result >= 0 )
    {
      if ( v6 )
        v5 = -1;
      else
        v5 = 0;
      *a2 = v5;
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids);
    return 2147942405LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004530  push    rbx
0x180004532  sub     rsp, 20h
0x180004536  mov     rbx, rdx
0x180004539  test    rdx, rdx
0x18000453c  jnz     short loc_180004545
0x18000453e  mov     eax, 80004003h
0x180004543  jmp     short loc_1800045B5
0x180004545  xor     eax, eax
0x180004547  mov     [rdx], ax
0x18000454a  cmp     [rcx+20h], al
0x18000454d  jnz     short loc_180004584
0x18000454f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004556  lea     rax, WPP_GLOBAL_Control
0x18000455d  cmp     rcx, rax
0x180004560  jz      short loc_18000457D
0x180004562  test    byte ptr [rcx+1Ch], 1
0x180004566  jz      short loc_18000457D
0x180004568  mov     rcx, [rcx+10h]
0x18000456c  lea     r8, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids
0x180004573  mov     edx, 0Ch
0x180004578  call    WPP_SF_
0x18000457d  mov     eax, 80070005h
0x180004582  jmp     short loc_1800045B5
0x180004584  mov     [rsp+28h+arg_8], eax
0x180004588  call    cs:__imp_MpUtilsExportFunctions
0x18000458e  lea     rdx, [rsp+28h+arg_8]
0x180004593  xor     ecx, ecx
0x180004595  mov     rax, [rax+60h]
0x180004599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459e  test    eax, eax
0x1800045a0  js      short loc_1800045B5
0x1800045a2  cmp     [rsp+28h+arg_8], 0
0x1800045a7  jz      short loc_1800045AE
0x1800045a9  or      eax, 0FFFFFFFFh
0x1800045ac  jmp     short loc_1800045B0
0x1800045ae  xor     eax, eax
0x1800045b0  mov     [rbx], ax
0x1800045b3  xor     eax, eax
0x1800045b5  add     rsp, 20h
0x1800045b9  pop     rbx
0x1800045ba  retn
```

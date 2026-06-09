# _commit

- ea: `0x14000b5e8`
- end: `0x14000b679`
- name: `_commit`
- size: `145`
- prototype: `int __cdecl(int FileHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a15c`

## callees

- `0x140006544`
- `0x14000689c`
- `0x14000b55c`
- `0x14000b5e8`

## pseudocode

```c
int __cdecl commit(int FileHandle)
{
  int *v2; // [rsp+20h] [rbp-18h] BYREF
  int v3; // [rsp+40h] [rbp+8h] BYREF
  char v4; // [rsp+48h] [rbp+10h] BYREF
  int v5; // [rsp+50h] [rbp+18h] BYREF
  int v6; // [rsp+58h] [rbp+20h] BYREF

  v3 = FileHandle;
  if ( FileHandle == -2 )
  {
    *(_DWORD *)sub_14000689C() = 9;
  }
  else
  {
    if ( FileHandle >= 0
      && FileHandle < (unsigned int)dword_14001AB50
      && (*(_BYTE *)(qword_14001A750[(__int64)FileHandle >> 6] + 72LL * (FileHandle & 0x3F) + 56) & 1) != 0 )
    {
      v5 = FileHandle;
      v6 = FileHandle;
      v2 = &v3;
      return ((__int64 (__fastcall *)(char *, int *, int **, int *))__crt_seh_guarded_call<int>::operator()<_lambda_a37b2b86f63e897a80ea819b0eb08c01_,_lambda_38ce7e780aa69e748d6df282ebc68efe_ &,_lambda_99fb1378e971ab6e7edea83e3a7a83a2_>)(
               &v4,
               &v6,
               &v2,
               &v5);
    }
    *(_DWORD *)sub_14000689C() = 9;
    invalid_parameter_noinfo();
  }
  return -1;
}

```

## disassembly

```asm
0x14000b5e8  mov     [rsp+arg_0], ecx
0x14000b5ec  sub     rsp, 38h
0x14000b5f0  movsxd  rdx, ecx
0x14000b5f3  cmp     edx, 0FFFFFFFEh
0x14000b5f6  jnz     short loc_14000B605
0x14000b5f8  call    sub_14000689C
0x14000b5fd  mov     dword ptr [rax], 9
0x14000b603  jmp     short loc_14000B671
0x14000b605  test    ecx, ecx
0x14000b607  js      short loc_14000B661
0x14000b609  cmp     edx, cs:dword_14001AB50
0x14000b60f  jnb     short loc_14000B661
0x14000b611  mov     rcx, rdx
0x14000b614  lea     r8, qword_14001A750
0x14000b61b  and     ecx, 3Fh
0x14000b61e  mov     rax, rdx
0x14000b621  sar     rax, 6
0x14000b625  lea     rcx, [rcx+rcx*8]
0x14000b629  mov     rax, [r8+rax*8]
0x14000b62d  test    byte ptr [rax+rcx*8+38h], 1
0x14000b632  jz      short loc_14000B661
0x14000b634  lea     rax, [rsp+38h+arg_0]
0x14000b639  mov     [rsp+38h+arg_10], edx
0x14000b63d  mov     [rsp+38h+arg_18], edx
0x14000b641  lea     r9, [rsp+38h+arg_10]
0x14000b646  lea     rdx, [rsp+38h+arg_18]
0x14000b64b  mov     [rsp+38h+var_18], rax
0x14000b650  lea     r8, [rsp+38h+var_18]
0x14000b655  lea     rcx, [rsp+38h+arg_8]
0x14000b65a  call    ??$?RV_lambda_a37b2b86f63e897a80ea819b0eb08c01_@@AEAV_lambda_38ce7e780aa69e748d6df282ebc68efe_@@V_lambda_99fb1378e971ab6e7edea83e3a7a83a2_@@@?$__crt_seh_guarded_call@H@@QEAAH$$QEAV_lambda_a37b2b86f63e897a80ea819b0eb08c01_@@AEAV_lambda_38ce7e780aa69e748d6df282ebc68efe_@@$$QEAV_lambda_99fb1378e971ab6e7edea83e3a7a83a2_@@@Z
0x14000b65f  jmp     short loc_14000B674
0x14000b661  call    sub_14000689C
0x14000b666  mov     dword ptr [rax], 9
0x14000b66c  call    _invalid_parameter_noinfo
0x14000b671  or      eax, 0FFFFFFFFh
0x14000b674  add     rsp, 38h
0x14000b678  retn
```

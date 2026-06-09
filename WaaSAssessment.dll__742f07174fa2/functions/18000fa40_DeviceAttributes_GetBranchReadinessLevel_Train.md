# DeviceAttributes::GetBranchReadinessLevel(Train &)

- ea: `0x18000fa40`
- end: `0x18000fae9`
- name: `?GetBranchReadinessLevel@DeviceAttributes@@UEAAJAEAW4Train@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, enum Train *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18000fa40`
- `0x18001752c`
- `0x180019290`
- `0x1800194f4`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetBranchReadinessLevel(DeviceAttributes *this, enum Train *a2)
{
  int v3; // edi
  _WORD *v4; // r8
  struct tagEnterprisePolicyValue_V1 *v6; // [rsp+38h] [rbp+10h] BYREF

  *(_DWORD *)a2 = 1;
  v6 = 0;
  v3 = ReadEnterprisePolicyValueWrapper(5u, &v6);
  if ( v3 >= 0 && *((_DWORD *)v6 + 1) == 1 && *((_WORD *)v6 + 8) == 8 )
  {
    v4 = (_WORD *)*((_QWORD *)v6 + 3);
    if ( *v4 == 67 && v4[1] == 66 && !v4[2] )
    {
      *(_DWORD *)a2 = 1;
      LogLevel(4u, (wchar_t *)L"Train = CB");
    }
  }
  if ( *(_DWORD *)a2 == 1 )
    LogLevel(4u, (wchar_t *)L"Train = CB");
  ReleaseEnterprisePolicyValueWrapper(&v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000fa40  mov     [rsp+arg_0], rbx
0x18000fa45  push    rdi
0x18000fa46  sub     rsp, 20h
0x18000fa4a  mov     rbx, rdx
0x18000fa4d  mov     dword ptr [rdx], 1
0x18000fa53  lea     rdx, [rsp+28h+arg_8]
0x18000fa58  mov     [rsp+28h+arg_8], 0
0x18000fa61  mov     ecx, 5
0x18000fa66  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000fa6b  mov     edi, eax
0x18000fa6d  test    eax, eax
0x18000fa6f  js      short loc_18000FABC
0x18000fa71  mov     rcx, [rsp+28h+arg_8]
0x18000fa76  cmp     dword ptr [rcx+4], 1
0x18000fa7a  jnz     short loc_18000FABC
0x18000fa7c  cmp     word ptr [rcx+10h], 8
0x18000fa81  jnz     short loc_18000FABC
0x18000fa83  mov     r8, [rcx+18h]
0x18000fa87  mov     eax, 43h ; 'C'
0x18000fa8c  cmp     ax, [r8]
0x18000fa90  jnz     short loc_18000FABC
0x18000fa92  mov     eax, 42h ; 'B'
0x18000fa97  cmp     ax, [r8+2]
0x18000fa9c  jnz     short loc_18000FABC
0x18000fa9e  xor     eax, eax
0x18000faa0  cmp     ax, [r8+4]
0x18000faa5  jnz     short loc_18000FABC
0x18000faa7  lea     rdx, aTrainCb; "Train = CB"
0x18000faae  mov     dword ptr [rbx], 1
0x18000fab4  lea     ecx, [rax+4]; unsigned __int8
0x18000fab7  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000fabc  cmp     dword ptr [rbx], 1
0x18000fabf  jnz     short loc_18000FAD2
0x18000fac1  lea     rdx, aTrainCb; "Train = CB"
0x18000fac8  mov     ecx, 4; unsigned __int8
0x18000facd  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000fad2  lea     rcx, [rsp+28h+arg_8]; struct tagEnterprisePolicyValue_V1 **
0x18000fad7  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x18000fadc  mov     rbx, [rsp+28h+arg_0]
0x18000fae1  mov     eax, edi
0x18000fae3  add     rsp, 20h
0x18000fae7  pop     rdi
0x18000fae8  retn
```

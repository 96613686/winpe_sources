# CXMLComparison::SaveMVKeys(IMVKey * *,ulong)

- ea: `0x18000f2fc`
- end: `0x18000f547`
- name: `?SaveMVKeys@CXMLComparison@@IEAAJPEAPEAUIMVKey@@K@Z`
- size: `587`
- prototype: `__int64 __fastcall(CXMLComparison *__hidden this, struct IMVKey **, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000cf20`

## callees

- `0x18000cd94`
- `0x18000da1c`
- `0x18000f2fc`
- `0x180010d44`
- `0x180010f4e`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f339`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f339`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000f39b`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000f39b`

## pseudocode

```c
__int64 __fastcall CXMLComparison::SaveMVKeys(CXMLComparison *this, struct IMVKey **a2, unsigned int a3)
{
  void *v6; // rax
  int ClassObject; // edi
  LPVOID v8; // rcx
  int v9; // esi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  LPVOID v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  __int64 v20; // [rsp+48h] [rbp-8h] BYREF
  int v21; // [rsp+90h] [rbp+40h] BYREF
  int v22; // [rsp+A8h] [rbp+58h] BYREF

  v21 = 0;
  v22 = 1;
  ppv = 0;
  *((_DWORD *)this + 26) = 0;
  v6 = CoTaskMemAlloc(8LL * *((unsigned int *)this + 23));
  *((_QWORD *)this + 12) = v6;
  if ( v6 )
  {
    memset_0(v6, 0, 8LL * *((unsigned int *)this + 23));
    v8 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    }
    ClassObject = CoGetClassObject(
                    &GUID_38be0989_9830_49a8_985b_7741219fd0fb,
                    1u,
                    0,
                    &GUID_00000001_0000_0000_c000_000000000046,
                    &ppv);
    if ( ClassObject >= 0 )
    {
      *((_DWORD *)this + 27) = 0;
LABEL_17:
      while ( 1 )
      {
        ClassObject = CXMLComparison::GetNextMatchComparison(this, (const unsigned __int16 **)&off_180019080, 7u, &v21);
        if ( ClassObject < 0 )
          break;
        if ( v21 )
        {
          if ( *((_DWORD *)this + 26) != *((_DWORD *)this + 23) )
            MicrosoftTelemetryAssertTriggeredNoArgs(v12);
          break;
        }
        v9 = 0;
        if ( a3 )
        {
          while ( 1 )
          {
            v20 = 0;
            v19 = 0;
            ClassObject = CXMLComparison::DoesKeyMatchCurrentXmlAttribute((__int64)this, (__int64 *)a2[v9], 1, &v22);
            if ( ClassObject < 0 )
              goto LABEL_27;
            if ( v22 == 3 )
            {
              v17 = 0;
              ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                              ppv,
                              0,
                              &GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0,
                              &v17);
              if ( ClassObject < 0 )
              {
                v14 = v17;
                if ( v17 )
                {
                  v17 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                }
              }
              else
              {
                (*(void (__fastcall **)(struct IMVKey *, __int64 *))(*(_QWORD *)a2[v9] + 40LL))(a2[v9], &v20);
                (*(void (__fastcall **)(struct IMVKey *, __int64 *))(*(_QWORD *)a2[v9] + 48LL))(a2[v9], &v19);
                ClassObject = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v17 + 24LL))(
                                v17,
                                v20,
                                v19);
                if ( ClassObject >= 0 )
                {
                  v10 = v17;
                  v17 = 0;
                  *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * (unsigned int)(*((_DWORD *)this + 26))++) = v10;
                  v11 = v17;
                  if ( v17 )
                  {
                    v17 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                  }
                  goto LABEL_17;
                }
                v13 = v17;
                if ( v17 )
                {
                  v17 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                }
              }
              goto LABEL_27;
            }
            if ( ++v9 >= a3 )
              goto LABEL_17;
          }
        }
      }
    }
  }
  else
  {
    ClassObject = -2147024882;
  }
LABEL_27:
  v15 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x18000f2fc  mov     [rsp-38h+arg_8], rbx
0x18000f301  push    rbp
0x18000f302  push    rsi
0x18000f303  push    rdi
0x18000f304  push    r12
0x18000f306  push    r13
0x18000f308  push    r14
0x18000f30a  push    r15
0x18000f30c  mov     rbp, rsp
0x18000f30f  sub     rsp, 50h
0x18000f313  mov     r14d, r8d
0x18000f316  mov     r12, rdx
0x18000f319  mov     rbx, rcx
0x18000f31c  xor     r13d, r13d
0x18000f31f  mov     [rbp+arg_0], r13d
0x18000f323  lea     edi, [r13+1]
0x18000f327  mov     [rbp+arg_18], edi
0x18000f32a  mov     [rbp+var_18], r13
0x18000f32e  mov     [rcx+68h], r13d
0x18000f332  mov     ecx, [rcx+5Ch]
0x18000f335  shl     rcx, 3; cb
0x18000f339  call    cs:__imp_CoTaskMemAlloc
0x18000f33f  mov     [rbx+60h], rax
0x18000f343  test    rax, rax
0x18000f346  jnz     short loc_18000F352
0x18000f348  mov     edi, 8007000Eh
0x18000f34d  jmp     loc_18000F513
0x18000f352  mov     r8d, [rbx+5Ch]
0x18000f356  shl     r8, 3; Size
0x18000f35a  xor     edx, edx; Val
0x18000f35c  mov     rcx, rax; void *
0x18000f35f  call    memset_0
0x18000f364  nop
0x18000f365  mov     rcx, [rbp+var_18]
0x18000f369  test    rcx, rcx
0x18000f36c  jz      short loc_18000F37F
0x18000f36e  mov     [rbp+var_18], r13
0x18000f372  mov     rax, [rcx]
0x18000f375  mov     rax, [rax+10h]
0x18000f379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f37e  nop
0x18000f37f  lea     rax, [rbp+var_18]
0x18000f383  mov     [rsp+50h+ppv], rax; ppv
0x18000f388  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000f38f  xor     r8d, r8d; pvReserved
0x18000f392  mov     edx, edi; dwClsContext
0x18000f394  lea     rcx, _GUID_38be0989_9830_49a8_985b_7741219fd0fb; rclsid
0x18000f39b  call    cs:__imp_CoGetClassObject
0x18000f3a1  mov     edi, eax
0x18000f3a3  test    eax, eax
0x18000f3a5  js      loc_18000F513
0x18000f3ab  mov     [rbx+6Ch], r13d
0x18000f3af  jmp     loc_18000F4A8
0x18000f3b4  cmp     [rbp+arg_0], r13d
0x18000f3b8  jnz     loc_18000F505
0x18000f3be  mov     esi, r13d
0x18000f3c1  test    r14d, r14d
0x18000f3c4  jz      loc_18000F4A8
0x18000f3ca  mov     [rbp+var_8], r13
0x18000f3ce  mov     [rbp+var_10], r13
0x18000f3d2  mov     r15d, esi
0x18000f3d5  lea     r9, [rbp+arg_18]
0x18000f3d9  mov     r8d, 1
0x18000f3df  mov     rdx, [r12+r15*8]
0x18000f3e3  mov     rcx, rbx
0x18000f3e6  call    ?DoesKeyMatchCurrentXmlAttribute@CXMLComparison@@QEAAJPEAUIMVKey@@W4FieldsRequiredForMatch@@PEAW4MatchType@@@Z; CXMLComparison::DoesKeyMatchCurrentXmlAttribute(IMVKey *,FieldsRequiredForMatch,MatchType *)
0x18000f3eb  mov     edi, eax
0x18000f3ed  test    eax, eax
0x18000f3ef  js      loc_18000F513
0x18000f3f5  cmp     [rbp+arg_18], 3
0x18000f3f9  jz      short loc_18000F407
0x18000f3fb  inc     esi
0x18000f3fd  cmp     esi, r14d
0x18000f400  jb      short loc_18000F3CA
0x18000f402  jmp     loc_18000F4A8
0x18000f407  mov     [rbp+var_20], r13
0x18000f40b  mov     rcx, [rbp+var_18]
0x18000f40f  mov     rax, [rcx]
0x18000f412  lea     r9, [rbp+var_20]
0x18000f416  lea     r8, _GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0
0x18000f41d  xor     edx, edx
0x18000f41f  mov     rax, [rax+18h]
0x18000f423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f428  mov     edi, eax
0x18000f42a  test    eax, eax
0x18000f42c  js      loc_18000F4E9
0x18000f432  mov     rcx, [r12+r15*8]
0x18000f436  mov     rax, [rcx]
0x18000f439  lea     rdx, [rbp+var_8]
0x18000f43d  mov     rax, [rax+28h]
0x18000f441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f446  mov     rcx, [r12+r15*8]
0x18000f44a  mov     rax, [rcx]
0x18000f44d  lea     rdx, [rbp+var_10]
0x18000f451  mov     rax, [rax+30h]
0x18000f455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f45a  mov     rcx, [rbp+var_20]
0x18000f45e  mov     rax, [rcx]
0x18000f461  mov     r8, [rbp+var_10]
0x18000f465  mov     rdx, [rbp+var_8]
0x18000f469  mov     rax, [rax+18h]
0x18000f46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f472  mov     edi, eax
0x18000f474  test    eax, eax
0x18000f476  js      short loc_18000F4CD
0x18000f478  mov     rdx, [rbp+var_20]
0x18000f47c  mov     [rbp+var_20], r13
0x18000f480  mov     ecx, [rbx+68h]
0x18000f483  mov     rax, [rbx+60h]
0x18000f487  mov     [rax+rcx*8], rdx
0x18000f48b  inc     dword ptr [rbx+68h]
0x18000f48e  mov     rcx, [rbp+var_20]
0x18000f492  test    rcx, rcx
0x18000f495  jz      short loc_18000F4A8
0x18000f497  mov     [rbp+var_20], r13
0x18000f49b  mov     rax, [rcx]
0x18000f49e  mov     rax, [rax+10h]
0x18000f4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a7  nop
0x18000f4a8  lea     r9, [rbp+arg_0]; int *
0x18000f4ac  mov     r8d, 7; unsigned int
0x18000f4b2  lea     rdx, off_180019080; unsigned __int16 **
0x18000f4b9  mov     rcx, rbx; this
0x18000f4bc  call    ?GetNextMatchComparison@CXMLComparison@@IEAAJPEAPEBGKPEAH@Z; CXMLComparison::GetNextMatchComparison(ushort const * *,ulong,int *)
0x18000f4c1  test    eax, eax
0x18000f4c3  mov     edi, eax
0x18000f4c5  jns     loc_18000F3B4
0x18000f4cb  jmp     short loc_18000F513
0x18000f4cd  mov     rcx, [rbp+var_20]
0x18000f4d1  test    rcx, rcx
0x18000f4d4  jz      short loc_18000F4E7
0x18000f4d6  mov     [rbp+var_20], r13
0x18000f4da  mov     rax, [rcx]
0x18000f4dd  mov     rax, [rax+10h]
0x18000f4e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4e6  nop
0x18000f4e7  jmp     short loc_18000F513
0x18000f4e9  mov     rcx, [rbp+var_20]
0x18000f4ed  test    rcx, rcx
0x18000f4f0  jz      short loc_18000F503
0x18000f4f2  mov     [rbp+var_20], r13
0x18000f4f6  mov     rax, [rcx]
0x18000f4f9  mov     rax, [rax+10h]
0x18000f4fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f502  nop
0x18000f503  jmp     short loc_18000F513
0x18000f505  mov     eax, [rbx+5Ch]
0x18000f508  cmp     [rbx+68h], eax
0x18000f50b  jz      short loc_18000F513
0x18000f50d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000f512  nop
0x18000f513  mov     rcx, [rbp+var_18]
0x18000f517  test    rcx, rcx
0x18000f51a  jz      short loc_18000F52D
0x18000f51c  mov     [rbp+var_18], r13
0x18000f520  mov     rax, [rcx]
0x18000f523  mov     rax, [rax+10h]
0x18000f527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f52c  nop
0x18000f52d  mov     eax, edi
0x18000f52f  mov     rbx, [rsp+50h+arg_8]
0x18000f537  add     rsp, 50h
0x18000f53b  pop     r15
0x18000f53d  pop     r14
0x18000f53f  pop     r13
0x18000f541  pop     r12
0x18000f543  pop     rdi
0x18000f544  pop     rsi
0x18000f545  pop     rbp
0x18000f546  retn
```

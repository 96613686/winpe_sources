# FwAuthAppsEnum::GetVariant(ulong,tagVARIANT *,FwEnumBase::GET_VARIANT_RESULT *)

- ea: `0x180002000`
- end: `0x1800021de`
- name: `?GetVariant@FwAuthAppsEnum@@EEAAJKPEAUtagVARIANT@@PEAW4GET_VARIANT_RESULT@FwEnumBase@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(FwAuthAppsEnum *__hidden this, unsigned int, struct tagVARIANT *, enum FwEnumBase::GET_VARIANT_RESULT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002000`
- `0x180002530`
- `0x1800277b0`

## import_xrefs

- `fwbase!FwBaseFree` at `0x1800020eb`
- `fwbase!FwBaseFree` at `0x1800020eb`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800020a4`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800020a4`
- `fwbase!IsRuleOldAuthApp` at `0x180002123`
- `fwbase!IsRuleOldAuthApp` at `0x180002123`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180002063`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180002063`
- `fwbase!FwReportReturnError` at `0x18000217c`
- `fwbase!FwReportReturnError` at `0x1800021d1`
- `fwbase!FwReportReturnError` at `0x18000217c`
- `fwbase!FwReportReturnError` at `0x1800021d1`

## pseudocode

```c
__int64 __fastcall FwAuthAppsEnum::GetVariant(
        FwAuthAppsEnum *this,
        int a2,
        struct tagVARIANT *a3,
        enum FwEnumBase::GET_VARIANT_RESULT *a4)
{
  _WORD *v4; // r13
  int v5; // r15d
  _QWORD **v8; // rbx
  int *v10; // r14
  int v11; // ebp
  _QWORD *v12; // rcx
  int ExpandedCanonicalLongPathName; // eax
  int v14; // ebx
  _WORD *v16; // rdx
  int v17; // ecx
  LONGLONG v19; // [rsp+28h] [rbp-60h] BYREF
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  int v21; // [rsp+38h] [rbp-50h] BYREF

  v4 = 0;
  v5 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v8 = (_QWORD **)((char *)this + 104);
  v10 = (int *)((char *)this + 112);
  if ( !a2 )
  {
    *v8 = (_QWORD *)*((_QWORD *)this + 11);
    *v10 = 0;
    *((_DWORD *)this + 29) = 0;
  }
  v11 = *v10;
  if ( (unsigned int)*v10 >= *((_DWORD *)this + 24) )
  {
LABEL_25:
    *(_DWORD *)a4 = 2;
    goto LABEL_13;
  }
  while ( 1 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(*v8) )
    {
      if ( (unsigned int)IsRuleOldAuthApp(*v8) )
      {
        v16 = *v8;
        if ( *((_WORD *)*v8 + 24) == 6 )
        {
          v17 = *((_DWORD *)this + 29);
          *((_DWORD *)this + 29) = v17 + 1;
          if ( a2 == v17 )
          {
            v4 = v16;
            v5 = 1;
          }
        }
      }
    }
    v12 = (_QWORD *)**v8;
    ++*v10;
    *v8 = v12;
    if ( v5 == 1 )
      break;
    if ( (unsigned int)++v11 >= *((_DWORD *)this + 24) )
      goto LABEL_25;
  }
  ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(*((_QWORD *)v4 + 34), &v20, &v21);
  v14 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_21;
  if ( !v21 )
    *(_DWORD *)a4 = 1;
  ExpandedCanonicalLongPathName = FwAuthApp::CreateInstance(*((unsigned int *)this + 18), v20, &v19);
  v14 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName == -2147024883 || ExpandedCanonicalLongPathName == -2147024894 )
  {
    *(_DWORD *)a4 = 1;
LABEL_13:
    v14 = 0;
    goto LABEL_14;
  }
  if ( ExpandedCanonicalLongPathName < 0 )
  {
LABEL_21:
    FwReportReturnError("FwAuthAppsEnum::GetVariant", (unsigned int)ExpandedCanonicalLongPathName);
    goto LABEL_14;
  }
  a3->llVal = v19;
  a3->vt = 9;
  *(_DWORD *)a4 = 0;
LABEL_14:
  FwBaseFree(v20);
  if ( v14 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthAppsEnum::GetVariant", (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180002000  mov     r11, rsp
0x180002003  mov     [r11+10h], rbx
0x180002007  push    rbp
0x180002008  push    rsi
0x180002009  push    rdi
0x18000200a  push    r12
0x18000200c  push    r13
0x18000200e  push    r14
0x180002010  push    r15
0x180002012  sub     rsp, 50h
0x180002016  mov     rax, cs:__security_cookie
0x18000201d  xor     rax, rsp
0x180002020  mov     [rsp+88h+var_48], rax
0x180002025  xor     r13d, r13d
0x180002028  mov     [rsp+88h+var_68], edx
0x18000202c  xor     r15d, r15d
0x18000202f  mov     [r11-60h], r13
0x180002033  mov     [r11-58h], r13
0x180002037  mov     rsi, r9
0x18000203a  mov     [r11-50h], r13d
0x18000203e  mov     r12, r8
0x180002041  lea     rbx, [rcx+68h]
0x180002045  mov     rdi, rcx
0x180002048  lea     r14, [rcx+70h]
0x18000204c  test    edx, edx
0x18000204e  jz      loc_180002160
0x180002054  mov     ebp, [r14]
0x180002057  cmp     ebp, [rcx+60h]
0x18000205a  jnb     loc_1800021BD
0x180002060  mov     rcx, [rbx]
0x180002063  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180002069  test    eax, eax
0x18000206b  jnz     loc_180002120
0x180002071  mov     rax, [rbx]
0x180002074  mov     rcx, [rax]
0x180002077  inc     dword ptr [r14]
0x18000207a  mov     [rbx], rcx
0x18000207d  cmp     r15d, 1
0x180002081  jz      short loc_180002093
0x180002083  inc     ebp
0x180002085  cmp     ebp, [rdi+60h]
0x180002088  jb      short loc_180002060
0x18000208a  test    r15d, r15d
0x18000208d  jz      loc_1800021BD
0x180002093  mov     rcx, [r13+110h]
0x18000209a  lea     r8, [rsp+88h+var_50]
0x18000209f  lea     rdx, [rsp+88h+var_58]
0x1800020a4  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x1800020aa  mov     ebx, eax
0x1800020ac  test    eax, eax
0x1800020ae  js      loc_180002173
0x1800020b4  cmp     [rsp+88h+var_50], 0
0x1800020b9  jz      loc_180002187
0x1800020bf  mov     rdx, [rsp+88h+var_58]
0x1800020c4  lea     r8, [rsp+88h+var_60]
0x1800020c9  mov     ecx, [rdi+48h]
0x1800020cc  call    ?CreateInstance@FwAuthApp@@SAJW4_tag_FW_PROFILE_TYPE@@PEBGPEAPEAV1@@Z; FwAuthApp::CreateInstance(_tag_FW_PROFILE_TYPE,ushort const *,FwAuthApp * *)
0x1800020d1  mov     ebx, eax
0x1800020d3  cmp     eax, 8007000Dh
0x1800020d8  jnz     loc_180002192
0x1800020de  mov     dword ptr [rsi], 1
0x1800020e4  xor     ebx, ebx
0x1800020e6  mov     rcx, [rsp+88h+var_58]
0x1800020eb  call    cs:__imp_FwBaseFree
0x1800020f1  test    ebx, ebx
0x1800020f3  js      loc_1800021C8
0x1800020f9  mov     eax, ebx
0x1800020fb  mov     rcx, [rsp+88h+var_48]
0x180002100  xor     rcx, rsp; StackCookie
0x180002103  call    __security_check_cookie
0x180002108  mov     rbx, [rsp+88h+arg_8]
0x180002110  add     rsp, 50h
0x180002114  pop     r15
0x180002116  pop     r14
0x180002118  pop     r13
0x18000211a  pop     r12
0x18000211c  pop     rdi
0x18000211d  pop     rsi
0x18000211e  pop     rbp
0x18000211f  retn
0x180002120  mov     rcx, [rbx]
0x180002123  call    cs:__imp_IsRuleOldAuthApp
0x180002129  test    eax, eax
0x18000212b  jz      loc_180002071
0x180002131  mov     rdx, [rbx]
0x180002134  cmp     word ptr [rdx+30h], 6
0x180002139  jnz     loc_180002071
0x18000213f  mov     ecx, [rdi+74h]
0x180002142  lea     eax, [rcx+1]
0x180002145  mov     [rdi+74h], eax
0x180002148  cmp     [rsp+88h+var_68], ecx
0x18000214c  jnz     loc_180002071
0x180002152  mov     r13, rdx
0x180002155  mov     r15d, 1
0x18000215b  jmp     loc_180002071
0x180002160  mov     rax, [rcx+58h]
0x180002164  mov     [rbx], rax
0x180002167  mov     [r14], r13d
0x18000216a  mov     [rcx+74h], r13d
0x18000216e  jmp     loc_180002054
0x180002173  mov     edx, eax
0x180002175  lea     rcx, aFwauthappsenum_1; "FwAuthAppsEnum::GetVariant"
0x18000217c  call    cs:__imp_FwReportReturnError
0x180002182  jmp     loc_1800020E6
0x180002187  mov     dword ptr [rsi], 1
0x18000218d  jmp     loc_1800020BF
0x180002192  cmp     eax, 80070002h
0x180002197  jz      loc_1800020DE
0x18000219d  test    eax, eax
0x18000219f  js      short loc_180002173
0x1800021a1  mov     rax, [rsp+88h+var_60]
0x1800021a6  mov     [r12+8], rax
0x1800021ab  mov     word ptr [r12], 9
0x1800021b2  mov     dword ptr [rsi], 0
0x1800021b8  jmp     loc_1800020E6
0x1800021bd  mov     dword ptr [rsi], 2
0x1800021c3  jmp     loc_1800020E4
0x1800021c8  mov     edx, ebx
0x1800021ca  lea     rcx, aFwauthappsenum_1; "FwAuthAppsEnum::GetVariant"
0x1800021d1  call    cs:__imp_FwReportReturnError
0x1800021d7  mov     ebx, eax
0x1800021d9  jmp     loc_1800020F9
```

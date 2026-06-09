# CPolicyCheck::AddPolicyEntry(ushort const *,ulong,ulong,ulong,ulong)

- ea: `0x180002e78`
- end: `0x180003006`
- name: `?AddPolicyEntry@CPolicyCheck@@QEAAJPEBGKKKK@Z`
- size: `398`
- prototype: `int(CPolicyCheck *__hidden this, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000300c`
- `0x18000401c`

## callees

- `0x1800017c0`
- `0x1800027b4`
- `0x180002c00`
- `0x180002e78`
- `0x180003228`
- `0x18000725c`
- `0x180015010`

## import_xrefs

- `urlmon!CreateUri` at `0x180002eaa`
- `urlmon!CreateUri` at `0x180002eaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPolicyCheck::AddPolicyEntry(
        CPolicyCheck *this,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6)
{
  HRESULT v10; // eax
  unsigned int v11; // esi
  _QWORD *v12; // rax
  _DWORD *v13; // rdi
  IUri *v14; // rdx
  void (__fastcall ***v16)(_QWORD, __int64); // [rsp+30h] [rbp-68h] BYREF
  IUri *ppURI; // [rsp+38h] [rbp-60h] BYREF
  ATL::CAtlException *v18; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v19[80]; // [rsp+48h] [rbp-50h] BYREF

  ppURI = 0;
  v10 = CreateUri(a2, 0, 0, &ppURI);
  v11 = v10;
  if ( v10 < 0 )
  {
    AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 3u, L"Invalid Policy Entry %s ignoring Error %x", a2, v10);
    v11 = -2147024883;
  }
  else
  {
    v12 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    try
    {
      v13 = v12;
      v16 = (void (__fastcall ***)(_QWORD, __int64))v12;
      if ( v12 )
      {
        v14 = ppURI;
        *v12 = &CPolicyEntry::`vftable';
        v12[1] = 0;
        v12[2] = 0;
        ATL::CComPtrBase<IUri>::Attach(v12 + 2, v14);
        v13[8] = a3;
        v13[7] = a4;
        v13[10] = a5;
        v13[9] = a6;
        v13[6] = 1;
        ATL::CComBSTR::operator=(v13 + 2, a2);
        v13[11] = 0;
      }
      else
      {
        v13 = 0;
      }
      v16 = (void (__fastcall ***)(_QWORD, __int64))v13;
      if ( v13 )
      {
        ppURI = 0;
        std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Emplace<CPolicyEntry * const &>(
          (char *)this + 112,
          v19,
          &v16);
        if ( v19[8] )
        {
          v11 = 0;
        }
        else
        {
          if ( v16 )
            (**v16)(v16, 1);
          v11 = -2147024713;
          AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 3u, L"Duplicate Policy Entry %s ignoring ", a2);
        }
      }
    }
    catch ( ATL::CAtlException *v18 )
    {
      LODWORD(v16) = *(_DWORD *)v18;
      v11 = (unsigned int)v16;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v16) = -2147024882;
      v11 = -2147024882;
    }
  }
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  return v11;
}

```

## disassembly

```asm
0x180002e78  push    rbx
0x180002e7a  push    rsi
0x180002e7b  push    rdi
0x180002e7c  push    r12
0x180002e7e  push    r13
0x180002e80  push    r14
0x180002e82  push    r15
0x180002e84  sub     rsp, 60h
0x180002e88  mov     r12d, r9d
0x180002e8b  mov     r13d, r8d
0x180002e8e  mov     r14, rdx
0x180002e91  mov     r15, rcx
0x180002e94  mov     [rsp+98h+ppURI], 0
0x180002e9d  lea     r9, [rsp+98h+ppURI]; ppURI
0x180002ea2  xor     r8d, r8d; dwReserved
0x180002ea5  xor     edx, edx; dwFlags
0x180002ea7  mov     rcx, r14; pwzURI
0x180002eaa  call    cs:__imp_CreateUri
0x180002eb0  mov     esi, eax
0x180002eb2  test    eax, eax
0x180002eb4  js      loc_180002FB4
0x180002eba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002ec1  mov     ecx, 30h ; '0'; unsigned __int64
0x180002ec6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002ecb  mov     rdi, rax
0x180002ece  mov     [rsp+98h+var_68], rax
0x180002ed3  test    rax, rax
0x180002ed6  jz      short loc_180002F37
0x180002ed8  mov     rdx, [rsp+98h+ppURI]
0x180002edd  lea     rax, ??_7CPolicyEntry@@6B@; const CPolicyEntry::`vftable'
0x180002ee4  mov     [rdi], rax
0x180002ee7  mov     qword ptr [rdi+8], 0
0x180002eef  lea     rcx, [rdi+10h]
0x180002ef3  mov     qword ptr [rcx], 0
0x180002efa  call    ?Attach@?$CComPtrBase@UIUri@@@ATL@@QEAAXPEAUIUri@@@Z; ATL::CComPtrBase<IUri>::Attach(IUri *)
0x180002eff  mov     [rdi+20h], r13d
0x180002f03  mov     [rdi+1Ch], r12d
0x180002f07  mov     eax, [rsp+98h+arg_20]
0x180002f0e  mov     [rdi+28h], eax
0x180002f11  mov     eax, [rsp+98h+arg_28]
0x180002f18  mov     [rdi+24h], eax
0x180002f1b  mov     dword ptr [rdi+18h], 1
0x180002f22  mov     rdx, r14
0x180002f25  lea     rcx, [rdi+8]
0x180002f29  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180002f2e  mov     dword ptr [rdi+2Ch], 0
0x180002f35  jmp     short loc_180002F39
0x180002f37  xor     edi, edi
0x180002f39  mov     [rsp+98h+var_68], rdi
0x180002f3e  test    rdi, rdi
0x180002f41  jz      short loc_180002FAA
0x180002f43  mov     [rsp+98h+ppURI], 0
0x180002f4c  lea     rcx, [r15+70h]
0x180002f50  lea     r8, [rsp+98h+var_68]
0x180002f55  lea     rdx, [rsp+98h+var_50]
0x180002f5a  call    ??$_Emplace@AEBQEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@_N@1@AEBQEAVCPolicyEntry@@@Z; std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Emplace<CPolicyEntry * const &>(CPolicyEntry * const &)
0x180002f5f  cmp     [rsp+98h+var_48], 0
0x180002f64  jnz     short loc_180002FA8
0x180002f66  mov     rcx, [rsp+98h+var_68]
0x180002f6b  test    rcx, rcx
0x180002f6e  jz      short loc_180002F80
0x180002f70  mov     rax, [rcx]
0x180002f73  mov     edx, 1
0x180002f78  mov     rax, [rax]
0x180002f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f80  mov     esi, 800700B7h
0x180002f85  mov     [rsp+98h+var_78], r14
0x180002f8a  lea     r9, aDuplicatePolic; "Duplicate Policy Entry %s ignoring "
0x180002f91  mov     edx, 8; unsigned int
0x180002f96  lea     r8d, [rdx-5]; unsigned __int8
0x180002f9a  lea     rcx, qword_180021AD8; this
0x180002fa1  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180002fa6  jmp     short loc_180002FAA
0x180002fa8  xor     esi, esi
0x180002faa  jmp     short loc_180002FDE
0x180002fac  jmp     short $+2
0x180002fae  mov     esi, dword ptr [rsp+98h+var_68]
0x180002fb2  jmp     short loc_180002FDE
0x180002fb4  mov     [rsp+98h+var_70], eax
0x180002fb8  mov     [rsp+98h+var_78], r14
0x180002fbd  lea     r9, aInvalidPolicyE; "Invalid Policy Entry %s ignoring Error "...
0x180002fc4  mov     edx, 8; unsigned int
0x180002fc9  lea     r8d, [rdx-5]; unsigned __int8
0x180002fcd  lea     rcx, qword_180021AD8; this
0x180002fd4  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180002fd9  mov     esi, 8007000Dh
0x180002fde  mov     rcx, [rsp+98h+ppURI]
0x180002fe3  test    rcx, rcx
0x180002fe6  jz      short loc_180002FF4
0x180002fe8  mov     rax, [rcx]
0x180002feb  mov     rax, [rax+10h]
0x180002fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff4  mov     eax, esi
0x180002ff6  add     rsp, 60h
0x180002ffa  pop     r15
0x180002ffc  pop     r14
0x180002ffe  pop     r13
0x180003000  pop     r12
0x180003002  pop     rdi
0x180003003  pop     rsi
0x180003004  pop     rbx
0x180003005  retn
```

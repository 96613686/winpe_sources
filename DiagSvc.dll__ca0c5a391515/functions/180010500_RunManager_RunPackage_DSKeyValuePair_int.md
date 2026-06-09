# RunManager::RunPackage(DSKeyValuePair * *,int *)

- ea: `0x180010500`
- end: `0x18001077c`
- name: `?RunPackage@RunManager@@MEAAJPEAPEAUDSKeyValuePair@@PEAH@Z`
- size: `636`
- prototype: `__int64 __fastcall(HSTRING *this, struct DSKeyValuePair **, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180010500`
- `0x18001134c`
- `0x1800127a8`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010680`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001056b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001060f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001075b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001056b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001060f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010662`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001075b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800105aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010643`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800105aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180010643`

## pseudocode

```c
__int64 __fastcall RunManager::RunPackage(HSTRING *this, struct DSKeyValuePair **a2, int *a3)
{
  int v6; // r15d
  __int64 (__fastcall *v7)(RunManager *, HSTRING *); // rbx
  HSTRING v8; // rsi
  __int64 (__fastcall *v9)(HSTRING, HSTRING, PCWSTR, HSTRING, __int64 *); // rdi
  HSTRING v10; // rbx
  PCWSTR StringRawBuffer; // rax
  int v12; // ebx
  HSTRING v13; // rdi
  __int64 (__fastcall *v14)(HSTRING, HSTRING *); // rbx
  HSTRING v15; // rsi
  __int64 (__fastcall *v16)(HSTRING, PCWSTR, __int64 ***); // rdi
  __int64 ***v17; // rbx
  PCWSTR v18; // rax
  int v19; // ebx
  __int64 v20; // rdx
  struct DSKeyValuePair *v21; // r8
  int v22; // edi
  __int64 *v23; // r11
  const unsigned __int16 *v24; // rax
  __int64 v25; // r8
  unsigned __int16 *v26; // r14
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r11
  const unsigned __int16 *v30; // rax
  __int64 *v31; // r11
  __int64 **v32; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 ***v36; // [rsp+30h] [rbp-10h] BYREF
  __int64 v37; // [rsp+38h] [rbp-8h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF
  HSTRING v39; // [rsp+98h] [rbp+58h] BYREF

  string = 0;
  v37 = 0;
  v36 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v6 = (*((__int64 (__fastcall **)(HSTRING *))*this + 15))(this);
    if ( v6 >= 0 )
    {
      v7 = (__int64 (__fastcall *)(RunManager *, HSTRING *))*((_QWORD *)*this + 17);
      WindowsDeleteString(string);
      string = 0;
      v6 = v7((RunManager *)this, &string);
      if ( v6 >= 0 )
      {
        v8 = this[10];
        v9 = *(__int64 (__fastcall **)(HSTRING, HSTRING, PCWSTR, HSTRING, __int64 *))(*(_QWORD *)v8 + 48LL);
        v10 = this[47];
        StringRawBuffer = WindowsGetStringRawBuffer(this[49], 0);
        v6 = v9(v8, string, StringRawBuffer, v10, &v37);
        if ( v37 )
        {
          v12 = (*(__int64 (__fastcall **)(HSTRING, __int64, __int64 ****))(*(_QWORD *)this[10] + 64LL))(
                  this[10],
                  v37,
                  &v36);
          if ( v12 < 0 )
            goto LABEL_23;
          v39 = 0;
          v13 = this[8];
          v14 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v13 + 56LL);
          WindowsDeleteString(0);
          v39 = 0;
          v12 = v14(v13, &v39);
          if ( v12 >= 0 )
          {
            v15 = this[10];
            v16 = *(__int64 (__fastcall **)(HSTRING, PCWSTR, __int64 ***))(*(_QWORD *)v15 + 72LL);
            v17 = v36;
            v18 = WindowsGetStringRawBuffer(v39, 0);
            v12 = v16(v15, v18, v17);
          }
          WindowsDeleteString(v39);
          if ( v12 < 0 )
          {
LABEL_23:
            v6 = v12;
          }
          else
          {
            v19 = *((_DWORD *)v36 + 2);
            v21 = (struct DSKeyValuePair *)calloc(v19, 0x3FCu);
            v39 = (HSTRING)v21;
            *a2 = v21;
            *a3 = v19;
            v22 = 0;
            v23 = **v36;
            while ( !*((_BYTE *)v23 + 25) )
            {
              v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                                v23 + 4,
                                                v20,
                                                v21);
              v26 = (unsigned __int16 *)(v25 + 1020LL * v22);
              v12 = StringCchCopyW(v26, 0xFFu, v24);
              if ( v12 < 0 )
                goto LABEL_23;
              v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                                v29 + 64,
                                                v27,
                                                v28);
              v12 = StringCchCopyW(v26 + 255, 0xFFu, v30);
              if ( v12 < 0 )
                goto LABEL_23;
              ++v22;
              v32 = (__int64 **)v31[2];
              if ( *((_BYTE *)v32 + 25) )
              {
                for ( i = (__int64 *)v31[1]; !*((_BYTE *)i + 25) && v31 == (__int64 *)i[2]; i = (__int64 *)i[1] )
                  v31 = i;
                v23 = i;
              }
              else
              {
                v23 = (__int64 *)v31[2];
                for ( j = *v32; !*((_BYTE *)j + 25); j = (__int64 *)*j )
                  v23 = j;
              }
              v21 = (struct DSKeyValuePair *)v39;
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  WindowsDeleteString(string);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010500  mov     [rsp-38h+arg_0], rbx
0x180010505  push    rbp
0x180010506  push    rsi
0x180010507  push    rdi
0x180010508  push    r12
0x18001050a  push    r13
0x18001050c  push    r14
0x18001050e  push    r15
0x180010510  mov     rbp, rsp
0x180010513  sub     rsp, 40h
0x180010517  mov     r12, r8
0x18001051a  mov     r13, rdx
0x18001051d  mov     r14, rcx
0x180010520  xor     edi, edi
0x180010522  mov     [rbp+string], rdi
0x180010526  mov     [rbp+var_8], rdi
0x18001052a  mov     [rbp+var_10], rdi
0x18001052e  test    rdx, rdx
0x180010531  jz      loc_180010751
0x180010537  test    r8, r8
0x18001053a  jz      loc_180010751
0x180010540  mov     [rdx], rdi
0x180010543  mov     [r8], edi
0x180010546  mov     rax, [rcx]
0x180010549  mov     rax, [rax+78h]
0x18001054d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010552  mov     r15d, eax
0x180010555  test    eax, eax
0x180010557  js      loc_180010757
0x18001055d  mov     rax, [r14]
0x180010560  mov     rbx, [rax+88h]
0x180010567  mov     rcx, [rbp+string]; string
0x18001056b  call    cs:__imp_WindowsDeleteString
0x180010571  mov     [rbp+string], rdi
0x180010575  lea     rdx, [rbp+string]
0x180010579  mov     rcx, r14
0x18001057c  mov     rax, rbx
0x18001057f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010584  mov     r15d, eax
0x180010587  test    eax, eax
0x180010589  js      loc_180010757
0x18001058f  mov     rsi, [r14+50h]
0x180010593  mov     rax, [rsi]
0x180010596  mov     rdi, [rax+30h]
0x18001059a  mov     rbx, [r14+178h]
0x1800105a1  xor     edx, edx; length
0x1800105a3  mov     rcx, [r14+188h]; string
0x1800105aa  call    cs:__imp_WindowsGetStringRawBuffer
0x1800105b0  lea     rcx, [rbp+var_8]
0x1800105b4  mov     [rsp+40h+var_20], rcx
0x1800105b9  mov     r9, rbx
0x1800105bc  mov     r8, rax
0x1800105bf  mov     rdx, [rbp+string]
0x1800105c3  mov     rcx, rsi
0x1800105c6  mov     rax, rdi
0x1800105c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ce  mov     r15d, eax
0x1800105d1  mov     rdx, [rbp+var_8]
0x1800105d5  xor     esi, esi
0x1800105d7  test    rdx, rdx
0x1800105da  jz      loc_180010757
0x1800105e0  mov     rcx, [r14+50h]
0x1800105e4  mov     rax, [rcx]
0x1800105e7  lea     r8, [rbp+var_10]
0x1800105eb  mov     rax, [rax+40h]
0x1800105ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105f4  mov     ebx, eax
0x1800105f6  test    eax, eax
0x1800105f8  js      loc_18001074C
0x1800105fe  mov     [rbp+arg_18], rsi
0x180010602  mov     rdi, [r14+40h]
0x180010606  mov     rax, [rdi]
0x180010609  mov     rbx, [rax+38h]
0x18001060d  xor     ecx, ecx; string
0x18001060f  call    cs:__imp_WindowsDeleteString
0x180010615  mov     [rbp+arg_18], rsi
0x180010619  lea     rdx, [rbp+arg_18]
0x18001061d  mov     rcx, rdi
0x180010620  mov     rax, rbx
0x180010623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010628  mov     ebx, eax
0x18001062a  test    eax, eax
0x18001062c  js      short loc_18001065E
0x18001062e  mov     rsi, [r14+50h]
0x180010632  mov     rax, [rsi]
0x180010635  mov     rdi, [rax+48h]
0x180010639  mov     rbx, [rbp+var_10]
0x18001063d  xor     edx, edx; length
0x18001063f  mov     rcx, [rbp+arg_18]; string
0x180010643  call    cs:__imp_WindowsGetStringRawBuffer
0x180010649  mov     r8, rbx
0x18001064c  mov     rdx, rax
0x18001064f  mov     rcx, rsi
0x180010652  mov     rax, rdi
0x180010655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001065a  mov     ebx, eax
0x18001065c  xor     esi, esi
0x18001065e  mov     rcx, [rbp+arg_18]; string
0x180010662  call    cs:__imp_WindowsDeleteString
0x180010668  test    ebx, ebx
0x18001066a  js      loc_18001074C
0x180010670  mov     rax, [rbp+var_10]
0x180010674  movsxd  rbx, dword ptr [rax+8]
0x180010678  mov     rcx, rbx; Count
0x18001067b  mov     edx, 3FCh; Size
0x180010680  call    cs:__imp_calloc
0x180010686  mov     r8, rax
0x180010689  mov     [rbp+arg_18], rax
0x18001068d  mov     [r13+0], rax
0x180010691  mov     [r12], ebx
0x180010695  mov     edi, esi
0x180010697  mov     rcx, [rbp+var_10]
0x18001069b  mov     r11, [rcx]
0x18001069e  mov     r11, [r11]
0x1800106a1  mov     r12d, 0FFh
0x1800106a7  cmp     [r11+19h], sil
0x1800106ab  jnz     loc_180010757
0x1800106b1  lea     rcx, [r11+20h]
0x1800106b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800106ba  movsxd  rcx, edi
0x1800106bd  imul    r14, rcx, 3FCh
0x1800106c4  add     r14, r8
0x1800106c7  mov     r8, rax; unsigned __int16 *
0x1800106ca  mov     rdx, r12; unsigned __int64
0x1800106cd  mov     rcx, r14; unsigned __int16 *
0x1800106d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800106d5  mov     ebx, eax
0x1800106d7  test    eax, eax
0x1800106d9  js      short loc_18001074C
0x1800106db  lea     rcx, [r11+40h]
0x1800106df  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800106e4  lea     rcx, [r14+1FEh]; unsigned __int16 *
0x1800106eb  mov     r8, rax; unsigned __int16 *
0x1800106ee  mov     rdx, r12; unsigned __int64
0x1800106f1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800106f6  mov     ebx, eax
0x1800106f8  xor     esi, esi
0x1800106fa  test    eax, eax
0x1800106fc  js      short loc_18001074C
0x1800106fe  inc     edi
0x180010700  mov     rcx, [r11+10h]
0x180010704  cmp     [rcx+19h], sil
0x180010708  jz      short loc_180010728
0x18001070a  mov     rax, [r11+8]
0x18001070e  jmp     short loc_18001071D
0x180010710  cmp     r11, [rax+10h]
0x180010714  jnz     short loc_180010723
0x180010716  mov     r11, rax
0x180010719  mov     rax, [rax+8]
0x18001071d  cmp     [rax+19h], sil
0x180010721  jz      short loc_180010710
0x180010723  mov     r11, rax
0x180010726  jmp     short loc_180010743
0x180010728  mov     r11, rcx
0x18001072b  mov     rcx, [rcx]
0x18001072e  cmp     [rcx+19h], sil
0x180010732  jnz     short loc_180010743
0x180010734  mov     r11, rcx
0x180010737  mov     rax, [rcx]
0x18001073a  mov     rcx, rax
0x18001073d  cmp     [rax+19h], sil
0x180010741  jz      short loc_180010734
0x180010743  mov     r8, [rbp+arg_18]
0x180010747  jmp     loc_1800106A7
0x18001074c  mov     r15d, ebx
0x18001074f  jmp     short loc_180010757
0x180010751  mov     r15d, 80070057h
0x180010757  mov     rcx, [rbp+string]; string
0x18001075b  call    cs:__imp_WindowsDeleteString
0x180010761  mov     eax, r15d
0x180010764  mov     rbx, [rsp+40h+arg_0]
0x18001076c  add     rsp, 40h
0x180010770  pop     r15
0x180010772  pop     r14
0x180010774  pop     r13
0x180010776  pop     r12
0x180010778  pop     rdi
0x180010779  pop     rsi
0x18001077a  pop     rbp
0x18001077b  retn
```

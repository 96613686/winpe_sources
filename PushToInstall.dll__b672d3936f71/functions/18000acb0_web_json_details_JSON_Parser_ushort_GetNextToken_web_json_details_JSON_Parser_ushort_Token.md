# web::json::details::JSON_Parser<ushort>::GetNextToken(web::json::details::JSON_Parser<ushort>::Token &)

- ea: `0x18000acb0`
- end: `0x18000b070`
- name: `?GetNextToken@?$JSON_Parser@G@details@json@web@@QEAAXAEAUToken@1234@@Z`
- size: `960`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009d30`
- `0x18000b1c0`
- `0x18000b390`
- `0x18000b7d0`

## callees

- `0x1800077f0`
- `0x18000a190`
- `0x18000acb0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000acfa`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000acfa`

## pseudocode

```c
char __fastcall web::json::details::JSON_Parser<unsigned short>::GetNextToken(int *a1, __int64 a2)
{
  web::json::details *v3; // rsi
  unsigned __int16 i; // bp
  web::json::details *v6; // rcx
  const struct web::json::details::json_error_category_impl *v7; // rax
  web::json::details *v8; // rcx
  int v9; // ecx
  int v10; // ecx
  web::json::details *v11; // rcx
  web::json::details *v12; // rcx
  web::json::details *v13; // rcx
  int v15; // [rsp+24h] [rbp-44h]

  v3 = (web::json::details *)(a2 + 8);
  while ( 2 )
  {
    for ( i = (**(__int64 (__fastcall ***)(int *))a1)(a1); i != 0xFFFF; i = (**(__int64 (__fastcall ***)(int *))a1)(a1) )
    {
      if ( !(unsigned int)_o_iswspace(i) )
        break;
    }
    *(_DWORD *)a2 = 0;
    v6 = v3;
    *(_QWORD *)(a2 + 40) = *((_QWORD *)a1 + 1);
    v7 = (const struct web::json::details::json_error_category_impl *)*((_QWORD *)a1 + 2);
    *(_QWORD *)(a2 + 48) = v7;
    *(_QWORD *)(a2 + 24) = 0;
    if ( *(_QWORD *)(a2 + 32) > 7u )
      v6 = *(web::json::details **)v3;
    *(_WORD *)v6 = 0;
    if ( i != 0xFFFF )
    {
      LOBYTE(v7) = i - 34;
      switch ( i )
      {
        case '"':
          LOBYTE(v7) = (*(__int64 (__fastcall **)(int *, __int64))(*(_QWORD *)a1 + 24LL))(a1, a2);
          if ( !(_BYTE)v7 )
          {
            v7 = web::json::details::json_error_category(v12);
            *(_DWORD *)(a2 + 72) = 7;
            goto LABEL_46;
          }
          return (char)v7;
        case ',':
          *(_DWORD *)a2 = 5;
          goto LABEL_16;
        case '-':
        case '0':
        case '1':
        case '2':
        case '3':
        case '4':
        case '5':
        case '6':
        case '7':
        case '8':
        case '9':
          LOBYTE(v7) = web::json::details::JSON_Parser<unsigned short>::CompleteNumberLiteral((__int64)a1, i, a2);
          if ( (_BYTE)v7 )
            return (char)v7;
          v7 = web::json::details::json_error_category(v13);
          *(_DWORD *)(a2 + 72) = 6;
          goto LABEL_46;
        case '/':
          if ( (*(unsigned __int8 (__fastcall **)(int *, __int64))(*(_QWORD *)a1 + 16LL))(a1, a2) )
            continue;
          v7 = web::json::details::json_error_category(v8);
          *(_DWORD *)(a2 + 72) = 3;
          goto LABEL_46;
        case ':':
          *(_DWORD *)a2 = 6;
          goto LABEL_16;
        case '[':
        case '{':
          if ( ++*((_QWORD *)a1 + 3) > 0x80u )
          {
            v7 = web::json::details::json_error_category(v6);
            *(_DWORD *)(a2 + 72) = 10;
            goto LABEL_46;
          }
          v9 = 3;
          LOBYTE(v7) = 1;
          if ( i == 123 )
            v9 = 1;
          *(_DWORD *)a2 = v9;
LABEL_16:
          *((_QWORD *)v3 + 2) = 0;
          if ( *((_QWORD *)v3 + 3) > 7u )
            v3 = *(web::json::details **)v3;
          goto LABEL_18;
        case ']':
        case '}':
          --*((_QWORD *)a1 + 3);
          if ( a1[6] < 0 )
          {
            v7 = web::json::details::json_error_category(v6);
            *(_DWORD *)(a2 + 72) = 9;
            goto LABEL_46;
          }
          v10 = 4;
          LOBYTE(v7) = 2;
          if ( i == 125 )
            v10 = 2;
          *(_DWORD *)a2 = v10;
          *((_QWORD *)v3 + 2) = 0;
          if ( *((_QWORD *)v3 + 3) <= 7u )
LABEL_18:
            *(_WORD *)v3 = 0;
          else
            **(_WORD **)v3 = 0;
          break;
        case 'f':
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 97 )
            goto LABEL_31;
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 108 )
            goto LABEL_31;
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 115 )
            goto LABEL_31;
          LOWORD(v7) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_WORD)v7 != 101 )
            goto LABEL_31;
          *(_DWORD *)a2 = 10;
          *(_BYTE *)(a2 + 56) = 0;
          return (char)v7;
        case 'n':
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 117 )
            goto LABEL_31;
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) != 108 )
            goto LABEL_31;
          LOWORD(v7) = (**(__int64 (__fastcall ***)(int *))a1)(a1);
          if ( (_WORD)v7 != 108 )
            goto LABEL_31;
          *(_DWORD *)a2 = 11;
          return (char)v7;
        case 't':
          if ( (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 114
            && (**(unsigned __int16 (__fastcall ***)(int *))a1)(a1) == 117
            && (LOWORD(v7) = (**(__int64 (__fastcall ***)(int *))a1)(a1), (_WORD)v7 == 101) )
          {
            *(_DWORD *)a2 = 10;
            *(_BYTE *)(a2 + 56) = 1;
          }
          else
          {
LABEL_31:
            v7 = web::json::details::json_error_category(v11);
            *(_DWORD *)(a2 + 72) = 4;
LABEL_46:
            *(_DWORD *)(a2 + 76) = v15;
            *(_QWORD *)(a2 + 80) = v7;
          }
          break;
        default:
          v7 = web::json::details::json_error_category(v6);
          *(_DWORD *)(a2 + 72) = 8;
          goto LABEL_46;
      }
    }
    return (char)v7;
  }
}

```

## disassembly

```asm
0x18000acb0  push    rbx
0x18000acb2  push    rbp
0x18000acb3  push    rsi
0x18000acb4  push    rdi
0x18000acb5  push    r12
0x18000acb7  push    r14
0x18000acb9  push    r15
0x18000acbb  sub     rsp, 30h
0x18000acbf  mov     rbx, rdx
0x18000acc2  lea     rsi, [rdx+8]
0x18000acc6  mov     rdi, rcx
0x18000acc9  lea     r12, __ImageBase
0x18000acd0  mov     r15d, 0FFFFh
0x18000acd6  xor     r14d, r14d
0x18000acd9  nop     dword ptr [rax+00000000h]
0x18000ace0  mov     rax, [rdi]
0x18000ace3  mov     rcx, rdi
0x18000ace6  mov     rax, [rax]
0x18000ace9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acee  movzx   ebp, ax
0x18000acf1  cmp     ax, r15w
0x18000acf5  jz      short loc_18000AD1B
0x18000acf7  movzx   ecx, bp
0x18000acfa  call    cs:__imp__o_iswspace
0x18000ad00  test    eax, eax
0x18000ad02  jz      short loc_18000AD1B
0x18000ad04  mov     rax, [rdi]
0x18000ad07  mov     rcx, rdi
0x18000ad0a  mov     rax, [rax]
0x18000ad0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad12  movzx   ebp, ax
0x18000ad15  cmp     ax, r15w
0x18000ad19  jnz     short loc_18000ACF7
0x18000ad1b  mov     [rbx], r14d
0x18000ad1e  mov     rcx, rsi
0x18000ad21  mov     rax, [rdi+8]
0x18000ad25  mov     [rbx+28h], rax
0x18000ad29  mov     rax, [rdi+10h]
0x18000ad2d  mov     [rbx+30h], rax
0x18000ad31  mov     [rbx+18h], r14
0x18000ad35  cmp     qword ptr [rbx+20h], 7
0x18000ad3a  jbe     short loc_18000AD3F
0x18000ad3c  mov     rcx, [rsi]; this
0x18000ad3f  mov     [rcx], r14w
0x18000ad43  cmp     bp, r15w
0x18000ad47  jz      loc_18000AFD8
0x18000ad4d  movzx   eax, bp
0x18000ad50  add     eax, 0FFFFFFDEh; switch 92 cases
0x18000ad53  cmp     eax, 5Bh
0x18000ad56  ja      def_18000AD72; jumptable 000000018000AD72 default case, cases 35-43,46,59-90,92,94-101,103-109,111-115,117-122,124
0x18000ad5c  cdqe
0x18000ad5e  movzx   eax, ds:(byte_18000B014 - 180000000h)[r12+rax]
0x18000ad67  mov     ecx, ds:(jpt_18000AD72 - 180000000h)[r12+rax*4]
0x18000ad6f  add     rcx, r12; this
0x18000ad72  jmp     rcx; switch jump
0x18000ad74  mov     rax, [rdi]; jumptable 000000018000AD72 case 47
0x18000ad77  mov     rdx, rbx
0x18000ad7a  mov     rcx, rdi
0x18000ad7d  mov     rax, [rax+10h]
0x18000ad81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad86  test    al, al
0x18000ad88  jnz     loc_18000ACE0
0x18000ad8e  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18000ad93  mov     dword ptr [rbx+48h], 3
0x18000ad9a  jmp     loc_18000AFCD
0x18000ad9f  inc     qword ptr [rdi+18h]; jumptable 000000018000AD72 cases 91,123
0x18000ada3  cmp     qword ptr [rdi+18h], 80h
0x18000adab  jbe     short loc_18000ADBE
0x18000adad  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18000adb2  mov     dword ptr [rbx+48h], 0Ah
0x18000adb9  jmp     loc_18000AFCD
0x18000adbe  cmp     bp, 7Bh ; '{'
0x18000adc2  mov     ecx, 3
0x18000adc7  mov     eax, 1
0x18000adcc  cmovz   ecx, eax
0x18000adcf  mov     [rbx], ecx
0x18000add1  mov     [rsi+10h], r14
0x18000add5  cmp     qword ptr [rsi+18h], 7
0x18000adda  jbe     short loc_18000ADDF
0x18000addc  mov     rsi, [rsi]
0x18000addf  mov     [rsi], r14w
0x18000ade3  add     rsp, 30h
0x18000ade7  pop     r15
0x18000ade9  pop     r14
0x18000adeb  pop     r12
0x18000aded  pop     rdi
0x18000adee  pop     rsi
0x18000adef  pop     rbp
0x18000adf0  pop     rbx
0x18000adf1  retn
0x18000adf2  dec     qword ptr [rdi+18h]; jumptable 000000018000AD72 cases 93,125
0x18000adf6  cmp     [rdi+18h], r14d
0x18000adfa  jge     short loc_18000AE0D
0x18000adfc  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18000ae01  mov     dword ptr [rbx+48h], 9
0x18000ae08  jmp     loc_18000AFCD
0x18000ae0d  cmp     bp, 7Dh ; '}'
0x18000ae11  mov     ecx, 4
0x18000ae16  mov     eax, 2
0x18000ae1b  cmovz   ecx, eax
0x18000ae1e  mov     [rbx], ecx
0x18000ae20  mov     [rsi+10h], r14
0x18000ae24  cmp     qword ptr [rsi+18h], 7
0x18000ae29  jbe     short loc_18000ADDF
0x18000ae2b  mov     rsi, [rsi]
0x18000ae2e  mov     [rsi], r14w
0x18000ae32  add     rsp, 30h
0x18000ae36  pop     r15
0x18000ae38  pop     r14
0x18000ae3a  pop     r12
0x18000ae3c  pop     rdi
0x18000ae3d  pop     rsi
0x18000ae3e  pop     rbp
0x18000ae3f  pop     rbx
0x18000ae40  retn
0x18000ae41  mov     dword ptr [rbx], 5; jumptable 000000018000AD72 case 44
0x18000ae47  jmp     short loc_18000ADD1
0x18000ae49  mov     dword ptr [rbx], 6; jumptable 000000018000AD72 case 58
0x18000ae4f  jmp     short loc_18000ADD1
0x18000ae51  mov     rax, [rdi]; jumptable 000000018000AD72 case 116
0x18000ae54  mov     rcx, rdi
0x18000ae57  mov     rax, [rax]
0x18000ae5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae5f  cmp     ax, 72h ; 'r'
0x18000ae63  jnz     short loc_18000AEA6
0x18000ae65  mov     rax, [rdi]
0x18000ae68  mov     rcx, rdi
0x18000ae6b  mov     rax, [rax]
0x18000ae6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae73  cmp     ax, 75h ; 'u'
0x18000ae77  jnz     short loc_18000AEA6
0x18000ae79  mov     rax, [rdi]
0x18000ae7c  mov     rcx, rdi
0x18000ae7f  mov     rax, [rax]
0x18000ae82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae87  cmp     ax, 65h ; 'e'
0x18000ae8b  jnz     short loc_18000AEA6
0x18000ae8d  mov     dword ptr [rbx], 0Ah
0x18000ae93  mov     byte ptr [rbx+38h], 1
0x18000ae97  add     rsp, 30h
0x18000ae9b  pop     r15
0x18000ae9d  pop     r14
0x18000ae9f  pop     r12
0x18000aea1  pop     rdi
0x18000aea2  pop     rsi
0x18000aea3  pop     rbp
0x18000aea4  pop     rbx
0x18000aea5  retn
0x18000aea6  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18000aeab  mov     dword ptr [rbx+48h], 4
0x18000aeb2  jmp     loc_18000AFCD
0x18000aeb7  mov     rax, [rdi]; jumptable 000000018000AD72 case 102
0x18000aeba  mov     rcx, rdi
0x18000aebd  mov     rax, [rax]
0x18000aec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec5  cmp     ax, 61h ; 'a'
0x18000aec9  jnz     short loc_18000AEA6
0x18000aecb  mov     rax, [rdi]
0x18000aece  mov     rcx, rdi
0x18000aed1  mov     rax, [rax]
0x18000aed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aed9  cmp     ax, 6Ch ; 'l'
0x18000aedd  jnz     short loc_18000AEA6
0x18000aedf  mov     rax, [rdi]
0x18000aee2  mov     rcx, rdi
0x18000aee5  mov     rax, [rax]
0x18000aee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeed  cmp     ax, 73h ; 's'
0x18000aef1  jnz     short loc_18000AEA6
0x18000aef3  mov     rax, [rdi]
0x18000aef6  mov     rcx, rdi
0x18000aef9  mov     rax, [rax]
0x18000aefc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af01  cmp     ax, 65h ; 'e'
0x18000af05  jnz     short loc_18000AEA6
0x18000af07  mov     dword ptr [rbx], 0Ah
0x18000af0d  mov     [rbx+38h], r14b
0x18000af11  add     rsp, 30h
0x18000af15  pop     r15
0x18000af17  pop     r14
0x18000af19  pop     r12
0x18000af1b  pop     rdi
0x18000af1c  pop     rsi
0x18000af1d  pop     rbp
0x18000af1e  pop     rbx
0x18000af1f  retn
0x18000af20  mov     rax, [rdi]; jumptable 000000018000AD72 case 110
0x18000af23  mov     rcx, rdi
0x18000af26  mov     rax, [rax]
0x18000af29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2e  cmp     ax, 75h ; 'u'
0x18000af32  jnz     loc_18000AEA6
0x18000af38  mov     rax, [rdi]
0x18000af3b  mov     rcx, rdi
0x18000af3e  mov     rax, [rax]
0x18000af41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af46  cmp     ax, 6Ch ; 'l'
0x18000af4a  jnz     loc_18000AEA6
0x18000af50  mov     rax, [rdi]
0x18000af53  mov     rcx, rdi
0x18000af56  mov     rax, [rax]
0x18000af59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af5e  cmp     ax, 6Ch ; 'l'
0x18000af62  jnz     loc_18000AEA6
0x18000af68  mov     dword ptr [rbx], 0Bh
0x18000af6e  add     rsp, 30h
0x18000af72  pop     r15
0x18000af74  pop     r14
0x18000af76  pop     r12
0x18000af78  pop     rdi
0x18000af79  pop     rsi
0x18000af7a  pop     rbp
0x18000af7b  pop     rbx
0x18000af7c  retn
0x18000af7d  mov     rax, [rdi]; jumptable 000000018000AD72 case 34
0x18000af80  mov     rdx, rbx
0x18000af83  mov     rcx, rdi
0x18000af86  mov     rax, [rax+18h]
0x18000af8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af8f  test    al, al
0x18000af91  jnz     short loc_18000AFD8
0x18000af93  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18000af98  mov     dword ptr [rbx+48h], 7
0x18000af9f  jmp     short loc_18000AFCD
0x18000afa1  mov     r8, rbx; jumptable 000000018000AD72 cases 45,48-57
0x18000afa4  movzx   edx, bp
0x18000afa7  mov     rcx, rdi
0x18000afaa  call    ?CompleteNumberLiteral@?$JSON_Parser@G@details@json@web@@AEAA_NGAEAUToken@1234@@Z; web::json::details::JSON_Parser<ushort>::CompleteNumberLiteral(ushort,web::json::details::JSON_Parser<ushort>::Token &)
0x18000afaf  test    al, al
0x18000afb1  jnz     short loc_18000AFD8
0x18000afb3  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; web::json::details::json_error_category(void)
0x18000afb8  mov     dword ptr [rbx+48h], 6
0x18000afbf  jmp     short loc_18000AFCD
0x18000afc1  call    ?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ; jumptable 000000018000AD72 default case, cases 35-43,46,59-90,92,94-101,103-109,111-115,117-122,124
0x18000afc6  mov     dword ptr [rbx+48h], 8
0x18000afcd  mov     ecx, [rsp+68h+var_44]
0x18000afd1  mov     [rbx+4Ch], ecx
0x18000afd4  mov     [rbx+50h], rax
0x18000afd8  add     rsp, 30h
0x18000afdc  pop     r15
0x18000afde  pop     r14
0x18000afe0  pop     r12
0x18000afe2  pop     rdi
0x18000afe3  pop     rsi
0x18000afe4  pop     rbp
0x18000afe5  pop     rbx
0x18000afe6  retn
```

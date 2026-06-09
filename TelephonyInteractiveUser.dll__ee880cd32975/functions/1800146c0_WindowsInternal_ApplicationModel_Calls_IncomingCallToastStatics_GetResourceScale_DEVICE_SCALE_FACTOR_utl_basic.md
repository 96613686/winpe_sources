# WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GetResourceScale(DEVICE_SCALE_FACTOR,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x1800146c0`
- end: `0x1800147a2`
- name: `?_GetResourceScale@IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJW4DEVICE_SCALE_FACTOR@@PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005a90`
- `0x180011e68`
- `0x1800146c0`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::_GetResourceScale(
        __int64 a1,
        int a2,
        __int64 a3)
{
  __int64 v3; // r8
  __int64 v4; // r9

  if ( a2 <= 300 )
  {
    if ( a2 <= 200 )
    {
      if ( a2 <= 150 )
      {
        if ( a2 <= 125 )
        {
          if ( a2 <= 100 )
          {
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     a3,
                                     L"100") )
            {
              v4 = 831;
              goto LABEL_4;
            }
          }
          else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                        a3,
                                        L"125") )
          {
            v4 = 827;
            goto LABEL_4;
          }
        }
        else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                      a3,
                                      L"150") )
        {
          v4 = 823;
          goto LABEL_4;
        }
      }
      else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                    a3,
                                    L"200") )
      {
        v4 = 819;
        goto LABEL_4;
      }
    }
    else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  a3,
                                  L"300") )
    {
      v4 = 815;
      goto LABEL_4;
    }
  }
  else if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                a3,
                                L"400") )
  {
    v4 = 811;
LABEL_4:
    Log_HREvent_1(2147942414LL, 0, v3, v4);
    return 2147942414LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800146c0  sub     rsp, 38h
0x1800146c4  mov     rcx, r8
0x1800146c7  cmp     edx, 12Ch
0x1800146cd  jle     short loc_1800146FF
0x1800146cf  lea     rdx, a400; "400"
0x1800146d6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800146db  test    al, al
0x1800146dd  jnz     loc_18001479B
0x1800146e3  mov     r9d, 32Bh
0x1800146e9  xor     edx, edx
0x1800146eb  mov     ecx, 8007000Eh
0x1800146f0  call    Log_HREvent_1
0x1800146f5  mov     eax, 8007000Eh
0x1800146fa  jmp     loc_18001479D
0x1800146ff  cmp     edx, 0C8h
0x180014705  jle     short loc_180014723
0x180014707  lea     rdx, a300; "300"
0x18001470e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180014713  test    al, al
0x180014715  jnz     loc_18001479B
0x18001471b  mov     r9d, 32Fh
0x180014721  jmp     short loc_1800146E9
0x180014723  cmp     edx, 96h
0x180014729  jle     short loc_180014743
0x18001472b  lea     rdx, a200; "200"
0x180014732  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180014737  test    al, al
0x180014739  jnz     short loc_18001479B
0x18001473b  mov     r9d, 333h
0x180014741  jmp     short loc_1800146E9
0x180014743  cmp     edx, 7Dh ; '}'
0x180014746  jle     short loc_180014760
0x180014748  lea     rdx, a150; "150"
0x18001474f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180014754  test    al, al
0x180014756  jnz     short loc_18001479B
0x180014758  mov     r9d, 337h
0x18001475e  jmp     short loc_1800146E9
0x180014760  cmp     edx, 64h ; 'd'
0x180014763  jle     short loc_180014780
0x180014765  lea     rdx, a125; "125"
0x18001476c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180014771  test    al, al
0x180014773  jnz     short loc_18001479B
0x180014775  mov     r9d, 33Bh
0x18001477b  jmp     loc_1800146E9
0x180014780  lea     rdx, a100; "100"
0x180014787  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18001478c  test    al, al
0x18001478e  jnz     short loc_18001479B
0x180014790  mov     r9d, 33Fh
0x180014796  jmp     loc_1800146E9
0x18001479b  xor     eax, eax
0x18001479d  add     rsp, 38h
0x1800147a1  retn
```
